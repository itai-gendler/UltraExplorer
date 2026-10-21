---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Change the text.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::preview
- text: A text draft holds the proposed contents and the source encoding while the file remains unchanged.
  kind: product
  entities:
  - entity: text-draft
    effect: creates
    facts:
    - Source
    - Text
    - Encoding
    to: Modified
  - entity: file
    effect: reads
    facts:
    - Path
    - Content
    - Read only
  actor: user
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
---

# Edit text in Quick Look

## Trigger

Quick Look has loaded an editable text file.

## Outcome

A text draft holds the proposed contents and the source encoding while the file remains unchanged.

## Edge cases

- Truncated, binary and read-only content is presented for inspection.
- The mini editor supports files up to 2 MiB.
