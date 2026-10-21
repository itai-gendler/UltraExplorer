---
appliesTo:
- type: entity
  id: text-draft
  effect: removes
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
---

# Users release their active text drafts

A draft is released when the person closes Quick Look after saving, or discards the retained edits.
