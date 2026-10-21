---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: The shelf is loaded or reactivated and entries are older than seven days or conclusively missing.
  kind: condition
  entities:
  - entity: shelf-item
    effect: reads
    facts:
    - Path
    - Added
    - Storage
    - Arrangement
  contexts:
    desktop:
      place: desktop::shelf
  unattended: true
- text: The obsolete shelf item is removed along with any owned copy; an unavailable volume alone does not remove an unexpired link.
  kind: product
  entities:
  - entity: shelf-item
    effect: removes
  contexts:
    desktop:
      place: desktop::shelf
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ShelfStore.cs
---

# Prune old or missing shelf content

## Trigger

The shelf is loaded or reactivated and entries are older than seven days or conclusively missing.

## Outcome

The obsolete shelf item is removed along with any owned copy; an unavailable volume alone does not remove an unexpired link.
