---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Remove the selected entries.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::shelf
- text: The shelf item is removed and any owned copy is deleted; a linked original remains untouched.
  kind: product
  entities:
  - entity: shelf-item
    effect: removes
  actor: user
  contexts:
    desktop:
      place: desktop::shelf
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ShelfStore.cs
---

# Remove items from the shelf

## Trigger

The person removes cards or clears the shelf.

## Outcome

The shelf item is removed and any owned copy is deleted; a linked original remains untouched.
