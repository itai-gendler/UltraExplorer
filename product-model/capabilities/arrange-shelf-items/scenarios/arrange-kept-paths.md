---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Rearrange the entries.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::shelf
- text: The shelf item arrangement is retained for later use.
  kind: product
  entities:
  - entity: shelf-item
    effect: changes
    facts:
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

# Arrange the collection

## Trigger

The person rearranges shelf cards.

## Outcome

The shelf item arrangement is retained for later use.
