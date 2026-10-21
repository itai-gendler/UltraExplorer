---
relations:
- entity: file
  verb: contains
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Models/FolderOrders.cs
---

# Folder

A filesystem directory, including a drive or share root, that holds files and other directories.

## Information kept

- **Name** — The displayed directory name.
- **Path** — Its filesystem location.
- **Modified** — Its last modification time.
- **Contents** — The files and child directories discovered there.
- **Listing status** — Whether contents are loaded, empty, capped or unavailable.
- **Hidden** — Whether filesystem attributes classify it as hidden or system.
- **Sort order** — The chosen ordering, or the default when no individual order applies.
