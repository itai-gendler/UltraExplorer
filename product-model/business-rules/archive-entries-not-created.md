---
appliesTo:
- type: entity
  id: archive-entry
  effect: creates
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.Archives.cs
permits: []
---

# File commands do not create entries inside archives

A transfer destination is a filesystem directory rather than a virtual archive folder.
