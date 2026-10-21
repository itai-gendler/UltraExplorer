---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Close Quick Look.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::preview
- text: Quick Look closes and the previous working context remains available.
  kind: product
  entities:
  - entity: file
    effect: reads
    facts:
    - Path
  actor: user
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
---

# Close an unchanged preview

## Trigger

The inspected contents have no unsaved edits.

## Outcome

The preview closes and the file workspace remains available.
