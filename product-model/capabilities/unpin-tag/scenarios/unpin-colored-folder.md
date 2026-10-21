---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Unpin the tag.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The mark loses its color, the Tags entry disappears and its note remains.
  kind: product
  entities:
  - entity: mark
    effect: changes
    facts:
    - Color
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Tags.cs
---

# Unpin a colored folder

## Trigger

The person chooses Unpin on a tag.

## Outcome

The mark loses its color, the Tags entry disappears and its note remains.
