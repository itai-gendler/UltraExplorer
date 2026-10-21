---
appliesTo:
- type: capability
  id: close-preview
- type: capability
  id: open-preview
- type: capability
  id: open-files
- type: capability
  id: open-with
- type: capability
  id: recycle-items
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs#CommitForCloseAsync
---

# Leaving editable text saves it before proceeding

Closing Quick Look, switching files, deleting the current file or opening an external application first attempts to save dirty editable text. Failure preserves the proposed edits and prevents that continuation.
