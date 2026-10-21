---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Discard changes.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::preview
- text: The text draft is removed and Quick Look closes without applying those edits.
  kind: product
  entities:
  - entity: text-draft
    effect: removes
    from: Conflict
  actor: user
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
---

# Discard a retained conflicting draft

## Trigger

A failed save has exposed Discard changes.

## Outcome

The text draft is removed and Quick Look closes without applying those edits.
