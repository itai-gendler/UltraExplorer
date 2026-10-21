---
appliesTo:
- type: entity
  id: workspace
  facts:
  - Selection
- type: capability
  id: select-items
- type: capability
  id: deselect-items
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Models/ItemSelection.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/ViewAllViewModel.cs
---

# File commands use the active pane’s selected paths

Canvas and list share one selection in each pane. Destructive actions use selected paths, while read-only actions may use the focus when selection is empty. A view or layer change does not silently discard the selected paths.
