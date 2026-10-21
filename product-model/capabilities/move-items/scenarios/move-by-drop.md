---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Drop the paths into the destination.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The selected file and folder paths move to the destination; confirmed unambiguous arrivals carry their mark paths, and the workspace releases the moved selection.
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

# Move into another folder

## Trigger

The person drops paths with a move effect.

## Outcome

The selected file and folder paths move to the destination; confirmed unambiguous arrivals carry their mark paths, and the workspace releases the moved selection.

## Edge cases

- A folder cannot be transferred into itself or a descendant.
- A destination-name collision does not cause a guessed relocation of its marks.
