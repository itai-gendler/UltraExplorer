---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Close Quick Look.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::preview
- text: The Product releases the saved text draft.
  kind: product
  actor: user
  entities:
  - entity: text-draft
    effect: removes
    from: Saved
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
---

# Close after an explicit save

## Trigger

The proposed text was already saved.

## Outcome

The saved draft is released as Quick Look closes.
