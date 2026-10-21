---
appliesTo:
- type: entity
  id: text-draft
  effect: changes
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
---

# Users change their active text drafts

The person’s editing, saving, closing and discard actions govern the drafts in their Quick Look session.
