---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Drop the temporary paths onto the shelf.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::shelf
- text: Each shelf item uses a shelf-owned copy so the content remains available after the temporary source is released.
  kind: product
  entities:
  - entity: shelf-item
    effect: creates
    facts:
    - Path
    - Added
    - Storage
    - Arrangement
  actor: user
  contexts:
    desktop:
      place: desktop::shelf
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ShelfStore.cs
---

# Retain temporary source content

## Trigger

Dropped paths would otherwise disappear with their temporary source.

## Outcome

Each shelf item uses a shelf-owned copy so the content remains available after the temporary source is released.

## Edge cases

- Earlier successfully added items remain if a later item fails.
