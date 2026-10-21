---
appliesTo:
- type: entity
  id: dialog-request
- type: capability
  id: choose-paths
- type: capability
  id: request-file-dialog
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogValidator.cs
---

# File-dialog acceptance returns paths and the caller writes content

The dialog chooses locations and checks the requested conditions. Accepting Save does not itself create the caller’s document or export.
