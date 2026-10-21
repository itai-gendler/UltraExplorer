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
- text: The mark is removed when its color is cleared because neither annotation remains.
  kind: product
  entities:
  - entity: mark
    effect: removes
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Tags.cs
---

# Remove a color-only annotation

## Trigger

A tagged path has no note.

## Outcome

The mark is removed when its color is cleared because neither annotation remains.
