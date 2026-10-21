---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Extract the archive without requesting a wrapper directory.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::files
- text: The Product reads the archive entry and publishes its single top-level file directly at the destination.
  kind: product
  actor: user
  entities:
  - entity: archive-entry
    effect: reads
    facts:
    - Path
    - Name
    - Kind
    - Size
    - Origin
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
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Archives/ArchiveService.cs#ExtractArchiveAsync
---

# Extract a single top-level file

## Trigger

A whole archive has one top-level file and an own-folder wrapper was not requested.

## Outcome

The file is extracted directly into the destination without an extra directory.
