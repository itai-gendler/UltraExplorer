---
appliesTo:
- type: entity
  id: shelf-item
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ShelfStore.cs
---

# Shelf links leave originals intact and temporary sources become copies

Adding an ordinary path creates a link. Temporary sources become owned copies. Removing or pruning a link does not delete its original; owned copies go with their entries. Entries expire after seven days.
