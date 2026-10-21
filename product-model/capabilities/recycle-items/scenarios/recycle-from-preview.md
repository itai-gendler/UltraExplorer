---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Recycle the inspected item.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::preview
- text: The Product removes the current file through Windows recycling.
  kind: product
  actor: user
  entities:
  - entity: file
    effect: removes
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs#DeleteCurrentAsync
---

# Recycle the inspected file

## Trigger

Quick Look shows an ordinary file.

## Outcome

The current file is recycled after pending text is saved, then Quick Look presents the next cached item or closes when none remains.
