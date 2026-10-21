---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Drop paths onto the shelf.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::shelf
- text: A shelf item is added as a link for each new existing path; repeated paths reuse their existing entry.
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

# Keep paths on the shelf

## Trigger

The shelf preference is enabled.

## Outcome

A shelf item is added as a link for each new existing path; repeated paths reuse their existing entry.
