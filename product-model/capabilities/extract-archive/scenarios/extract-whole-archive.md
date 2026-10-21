---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose whole-archive extraction and its destination.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::files
- text: The Product reads the archive entry contents and publishes the extracted folder with its contents.
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
  - entity: folder
    effect: creates
    facts:
    - Name
    - Path
    - Contents
    - Listing status
    - Modified
    - Hidden
    - Sort order
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Archives/ArchiveService.cs#ExtractArchiveAsync
---

# Extract a whole archive without scattering contents

## Trigger

The person extracts an archive with multiple top-level entries, or explicitly requests its own destination directory.

## Outcome

The extracted contents are grouped in an archive-named directory. A single top-level directory can instead be published directly when an own-folder wrapper was not requested.
