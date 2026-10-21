---
appliesTo:
- type: entity
  id: dialog-request
  effect: changes
  facts:
  - Application options
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.NativeProxy.cs
permits:
- actors:
  - user
---

# Users edit the application options offered by the caller

The person may set the caller’s supported extra options during the active choice.
