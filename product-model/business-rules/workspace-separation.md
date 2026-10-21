---
appliesTo:
- type: entity
  id: workspace
  facts:
  - Saved arrangement
- type: capability
  id: save-workspace
- type: capability
  id: restore-workspace
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs#SaveNowCoreAsync
---

# Picker sessions preserve the ordinary saved canvas

The ordinary arrangement and the standalone picker’s arrangement are kept apart. A file dialog that stands in for an application’s Windows dialog never saves its canvas or session over them, while favorites, colors and notes changed there are still saved.
