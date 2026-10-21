---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Revise the text.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::preview
- text: The text draft holds the new proposed contents.
  kind: product
  actor: user
  entities:
  - entity: text-draft
    effect: changes
    facts:
    - Text
    from: Saved
    to: Modified
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
---

# Revise previously saved text

## Trigger

The text editor still displays a saved draft.

## Outcome

The new edit becomes another unsaved change.
