---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Copy the selection.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The existing selected file and folder paths are placed on the clipboard as a copy payload; the source items stay in place.
  kind: product
  entities:
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
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/NativeShellService.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ShellFileOperation.cs
---

# Prepare a clipboard copy

## Trigger

The person copies selected paths.

## Outcome

The existing selected file and folder paths are placed on the clipboard as a copy payload; the source items stay in place.

## Edge cases

- Missing selections and an unavailable clipboard produce an error.
