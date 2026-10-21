---
appliesTo:
- type: entity
  id: shelf-item
  effect: removes
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ShelfStore.cs
permits:
- actors:
  - user
  when:
  - entity: settings
    fact: Shelf
    is: true
- unattended: true
---

# Users remove visible shelf items and the Product prunes expired entries

User removal is available while the shelf is enabled. The Product also removes entries when their retention period ends or their source is conclusively gone.
