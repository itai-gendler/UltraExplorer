---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Choose a program target for the selected paths.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::files
- text: The selected file paths are handed to the chosen supported program target as input.
  kind: product
  actor: user
  entities:
  - entity: file
    effect: reads
    facts:
    - Path
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Drag.cs#CompleteNodeDropAsync
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/NativeShellService.cs#OpenWithProgramAsync
---

# Open selected paths with a program target

## Trigger

The person drops selected paths onto a supported program target.

## Outcome

The program receives the selected paths; an unavailable or unsupported target produces an error.

