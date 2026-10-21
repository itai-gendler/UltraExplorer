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
- text: The file receives the changed contents and the text draft becomes saved.
  kind: product
  actor: user
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
    - Size
    - Modified
  - entity: text-draft
    effect: changes
    facts:
    - Text
    from: Modified
    to: Saved
  contexts:
    desktop:
      place: desktop::preview
- text: The Product releases the saved text draft and closes Quick Look.
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
  target: src/UltraExplorer/QuickPreviewWindow.cs#OnClosing
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs#CommitForCloseAsync
- kind: doc
  role: intent
  target: docs/UNIVERSAL_PREVIEWS.md
---

# Save before leaving Quick Look

## Trigger

Editable text has unsaved changes and the person closes Quick Look.

## Outcome

The changes are saved in the original encoding before closing; a failed save keeps the edits available.
