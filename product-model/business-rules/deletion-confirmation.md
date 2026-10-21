---
appliesTo:
- type: capability
  id: delete-items
- type: capability
  id: recycle-items
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs#ConfirmUnshownSelection
---

# Permanent deletion and unseen selections require confirmation

Permanent deletion requires an explicit confirmation. Either deletion action also asks about selected paths the current canvas does not show when that count is known.
