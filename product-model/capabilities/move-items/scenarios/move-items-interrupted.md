---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Start the requested transfer.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The affected folder listings are refreshed and an interruption or error is reported; completed file transfers remain on disk and confirmed moved mark paths are reconciled.
  kind: product
  entities:
  - entity: folder
    effect: changes
    facts:
    - Contents
    - Listing status
  - entity: file
    effect: reads
    facts:
    - Path
  - entity: mark
    effect: changes
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

# Move interrupted

## Trigger

Windows cancels or fails a transfer after it has started.

## Outcome

The affected folder listings are refreshed and an interruption or error is reported; completed file transfers remain on disk and confirmed moved mark paths are reconciled.
