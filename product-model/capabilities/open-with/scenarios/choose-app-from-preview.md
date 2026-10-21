---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Open in the requested application.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::preview
- text: The file is handed to the chosen application after pending editable text is saved.
  kind: product
  actor: user
  entities:
  - entity: file
    effect: reads
    facts:
    - Path
    - Type
    - Content
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs#OpenExternalAsync
---

# Choose an application from Quick Look

## Trigger

The person uses an external-open action in Quick Look.

## Outcome

The file is handed to the chosen application after pending editable text is saved.

## Edge cases

- A failed text save leaves Quick Look and the proposed edits available.
- For an archive preview, the external action opens the extracted temporary copy.
