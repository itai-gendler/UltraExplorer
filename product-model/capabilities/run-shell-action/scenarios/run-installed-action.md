---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Request actions for the selection.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::files
- text: The chosen action is invoked through the installed Windows Shell provider for the selected file and folder paths.
  kind: product
  actor: user
  entities:
  - entity: file
    effect: reads
    facts:
    - Path
  - entity: folder
    effect: reads
    facts:
    - Path
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.ShellMenus.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ShellContextMenu.cs
---

# Invoke an installed Shell action

## Trigger

A same-parent selection has an available Shell action.

## Outcome

The chosen action is invoked through the installed Windows Shell provider for the selected file and folder paths.
