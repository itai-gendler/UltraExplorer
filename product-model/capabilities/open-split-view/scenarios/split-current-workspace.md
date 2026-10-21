---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Open the split view.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace opens a second independent pane and retains each pane’s camera, selection, filter and history.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Split
    - Locations
    - Selection
    - Camera
    - Filter
    - History
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Split.cs
---

# Open a second location

## Trigger

The person requests a split.

## Outcome

The workspace opens a second independent pane and retains each pane’s camera, selection, filter and history.

## Edge cases

- Opening a folder in the other pane creates the split if necessary and leaves the original pane active.
- Split panes are offered in nested ordinary contexts, not file dialogs.
