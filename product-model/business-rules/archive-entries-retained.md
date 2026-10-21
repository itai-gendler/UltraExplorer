---
appliesTo:
- type: entity
  id: archive-entry
  effect: removes
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.Archives.cs
permits: []
---

# Archive entries are not removed through file commands

Extracted copies can be used as ordinary files; entries inside the archive are retained.
