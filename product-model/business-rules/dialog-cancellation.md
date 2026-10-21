---
appliesTo:
- type: entity
  id: dialog-request
  effect: changes
  to: Cancelled
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Picker.cs
permits:
- actors:
  - user
---

# Users may cancel a pending file choice

Cancelling ends the request without accepted paths.
