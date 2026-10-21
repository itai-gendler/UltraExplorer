---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose the neighboring item.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::preview
- text: The Product presents the neighboring file contents.
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
  target: src/UltraExplorer/QuickPreviewWindow.cs#NavigateFileAsync
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs#SaveAndOpenAsync
---

# Inspect another file in Quick Look

## Trigger

The person chooses the previous or next file from the cached current location.

## Outcome

Quick Look presents the neighboring file after saving any dirty editable text; it stays on the current contents if saving fails.

## Edge cases

- At either end of the cached sequence there is no next item in that direction.
- Closing or switching media stops the owned player.
