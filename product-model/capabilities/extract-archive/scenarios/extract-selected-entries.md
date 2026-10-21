---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose the entries and extraction destination.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The Product creates the requested standalone file copies.
  kind: product
  entities:
  - entity: file
    effect: creates
    facts:
    - Name
    - Path
    - Size
    - Modified
    - Type
    - Content
    - Hidden
    - Read only
    - Preview editing
  actor: user
  contexts: &id001
    desktop:
      place: desktop::files
- text: The Product creates the requested folder copies with their contents.
  kind: product
  entities:
  - entity: archive-entry
    effect: reads
    facts:
    - Path
    - Name
    - Kind
    - Size
    - Origin
  - entity: folder
    effect: creates
    facts:
    - Name
    - Path
    - Modified
    - Contents
    - Listing status
    - Hidden
    - Sort order
  actor: user
  contexts: *id001
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.Archives.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Archives/ArchiveService.cs
---

# Extract archive contents

## Trigger

The person requests extraction or drags entries to a filesystem destination.

## Outcome

The archive entry contents are copied into new file and folder paths at the chosen destination, leaving the archive unchanged.

## Edge cases

- Extraction may target the archive’s parent, a separate folder or a chosen location.
- Encrypted content asks for a password; cancellation leaves the request unfinished.
- A missing extraction provider, invalid password or unsupported archive produces a reported error.
