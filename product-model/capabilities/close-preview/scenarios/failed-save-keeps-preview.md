---
kind: edge
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
- text: The text draft retains its edits in conflict while the file remains unchanged.
  kind: product
  actor: user
  entities:
  - entity: text-draft
    effect: changes
    facts: []
    from: Modified
    to: Conflict
  - entity: file
    effect: reads
    facts:
    - Content
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
---

# Keep edits when close cannot save

## Trigger

The person closes Quick Look after the source changed elsewhere.

## Outcome

Quick Look remains open with the proposed text and a reported conflict.
