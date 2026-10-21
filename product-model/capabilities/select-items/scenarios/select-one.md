---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose one item.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace selection contains that file or folder, with its focus and range anchor; the canvas and list agree.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Selection
  - entity: file
    effect: reads
    facts:
    - Name
    - Path
    - Size
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
  target: src/UltraExplorer/Models/ItemSelection.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Controls/NestedCanvas.Selection.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Selection.cs
---

# Select one item

## Trigger

The person chooses one displayed item.

## Outcome

The workspace selection contains that file or folder, with its focus and range anchor; the canvas and list agree.
