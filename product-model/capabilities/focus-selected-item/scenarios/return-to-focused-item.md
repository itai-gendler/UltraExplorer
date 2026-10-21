---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Ask to bring the focused selected item back into view.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace camera centers the focused selected file or folder while preserving selection and history.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Camera
  - entity: file
    effect: reads
    facts:
    - Path
  - entity: folder
    effect: reads
    facts:
    - Path
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Focus.cs
---

# Return to the focused item

## Trigger

A selected item is distant or too small to inspect.

## Outcome

The workspace camera centers the focused selected file or folder while preserving selection and history.
