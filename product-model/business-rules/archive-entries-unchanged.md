---
appliesTo:
- type: entity
  id: archive-entry
  effect: changes
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.Archives.cs
permits: []
---

# Archive entries are not edited in place

Archive browsing and extraction leave the archive’s virtual entries unchanged.
