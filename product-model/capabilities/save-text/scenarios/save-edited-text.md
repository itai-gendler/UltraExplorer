---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Save the edits.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::preview
- text: The file content is replaced with the proposed text in its original encoding and the text draft becomes saved.
  kind: product
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
  actor: user
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/PreviewTextEditSession.cs
---

# Save edited text

## Trigger

A modified draft is ready to save.

## Outcome

The file content is replaced with the proposed text in its original encoding and the text draft becomes saved.
