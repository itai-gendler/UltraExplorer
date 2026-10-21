---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Extend a range, toggle members, select all or sweep an area.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace selection contains the requested group of file and folder paths and reports file bytes and item totals; extending a range does not add a navigation-history entry per item.
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

# Select a group

## Trigger

The person extends, toggles or sweeps a selection.

## Outcome

The workspace selection contains the requested group of file and folder paths and reports file bytes and item totals; extending a range does not add a navigation-history entry per item.

## Edge cases

- A range and area selection are bounded by their containing folder and the visible matching entries.
- Clearing visibility layers does not itself clear previously selected paths.
