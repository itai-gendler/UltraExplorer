---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Show properties.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: Windows presents properties for a same-parent selection, or the first item when a combined sheet is unavailable.
  kind: product
  entities:
  - entity: file
    effect: reads
    facts:
    - Name
    - Path
    - Size
    - Modified
    - Type
    - Content
    - Hidden
    - Read only
  - entity: folder
    effect: reads
    facts:
    - Name
    - Path
    - Modified
    - Contents
    - Listing status
    - Hidden
    - Sort order
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# Inspect filesystem properties

## Trigger

The person requests properties.

## Outcome

Windows presents properties for a same-parent selection, or the first item when a combined sheet is unavailable.
