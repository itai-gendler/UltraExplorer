---
appliesTo:
- type: entity
  id: folder
  facts:
  - Sort order
- type: capability
  id: browse-files
- type: capability
  id: change-sorting-settings
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Models/FolderOrders.cs
---

# Individual folder orders do not inherit into descendants

Per-folder sorting applies only to the named folder. All-folder scope retains dormant individual orders. At most 5,000 most-recently-sorted individual orders are remembered.
