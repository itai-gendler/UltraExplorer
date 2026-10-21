---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Request a reveal of the selection.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The folder window reveals the same-parent selection where supported, otherwise the first selected item.
  kind: product
  entities:
  - entity: file
    effect: reads
    facts:
    - Path
  - entity: folder
    effect: reads
    facts:
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

# Reveal a selection in a folder window

## Trigger

The person requests Show in Explorer.

## Outcome

The folder window reveals the same-parent selection where supported, otherwise the first selected item.
