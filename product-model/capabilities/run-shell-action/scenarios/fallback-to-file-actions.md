---
kind: edge
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
- text: UltraExplorer offers its own file and folder actions for the selection.
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

# Use app actions when Shell actions are unavailable

## Trigger

A selection spans several parents, is too large for the native action set, or its provider is unavailable.

## Outcome

UltraExplorer offers its own file and folder actions for the selection.
