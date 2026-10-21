---
appliesTo:
- type: entity
  id: dialog-request
  effect: changes
  facts:
  - Filename
  - Interaction
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogSession.cs
permits:
- actors:
  - user
---

# Users edit the input of their active file choice

The person may supply or replace the pending name and interaction values.
