---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Pin the locations.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: A favorite is retained for each existing folder not already pinned.
  kind: product
  entities:
  - entity: favorite
    effect: creates
    facts:
    - Name
    - Path
  - entity: folder
    effect: reads
    facts:
    - Name
    - Path
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# Pin folders for quick access

## Trigger

The person pins selected folders.

## Outcome

A favorite is retained for each existing folder not already pinned.
