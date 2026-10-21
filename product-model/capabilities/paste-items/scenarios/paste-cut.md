---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Paste into the target location.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The file and folder paths move to the target; the unchanged cut payload is cleared only once all its original paths are gone.
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Path
  - entity: folder
    effect: changes
    facts:
    - Path
  - entity: mark
    effect: changes
    facts:
    - Path
  - entity: workspace
    effect: changes
    facts:
    - Selection
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/NativeShellService.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ShellFileOperation.cs
---

# Paste a move payload

## Trigger

The clipboard contains paths prepared for moving.

## Outcome

The file and folder paths move to the target; the unchanged cut payload is cleared only once all its original paths are gone.

## Edge cases

- A newer clipboard value is preserved.
- A partial move leaves its unfinished cut payload available.
