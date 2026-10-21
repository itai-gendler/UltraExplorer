---
appliesTo:
- type: capability
  id: copy-items
- type: capability
  id: move-items
- type: capability
  id: paste-items
- type: capability
  id: duplicate-items
- type: capability
  id: recycle-items
- type: capability
  id: delete-items
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ShellFileOperation.cs
---

# Windows Shell decides transfer conflicts and cancellation

Copy, move, paste, duplication and deletion use Windows Shell outcomes and refresh affected locations after an interruption. A cancelled batch can have completed individual transfers.
