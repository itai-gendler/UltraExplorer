---
appliesTo:
- type: capability
  id: create-folder
- type: capability
  id: create-text-file
- type: capability
  id: paste-items
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/ViewAllViewModel.cs#TargetDirectory
---

# New items and pasted items use the current target folder

Several selected siblings target their common parent. Otherwise a focused folder targets itself and a focused file targets its parent. Commands report when no usable target exists.
