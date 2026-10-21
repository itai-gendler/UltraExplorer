---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Navigate into a supported archive.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::files
- text: The workspace presents archive entry contents as navigable locations on the nested canvas.
  kind: product
  actor: user
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Locations
    - Camera
  - entity: archive-entry
    effect: reads
    facts:
    - Name
    - Path
    - Kind
    - Size
    - Origin
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Archives/ArchiveService.cs#TryRead
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.OptionalFeatures.cs
---

# Browse archive contents

## Trigger

Archive browsing is enabled and the person opens a supported archive on the nested canvas.

## Outcome

The contents can be navigated and inspected as archive entries.

## Edge cases

- Encrypted content can require a password.
- An unavailable archive provider or unreadable archive is reported.
- Tree view treats the archive as an ordinary file while retaining the saved preference.
