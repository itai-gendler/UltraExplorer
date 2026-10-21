---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Press Esc or click outside any item.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace selection becomes empty while the focus and range anchor remain available.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Selection
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Models/ItemSelection.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Controls/NestedCanvas.Selection.cs#ClearSelection
---

# Clear selected paths

## Trigger

The person presses Esc or clicks outside any item while paths are selected.

## Outcome

The workspace selection becomes empty while the focus and range anchor remain available.
