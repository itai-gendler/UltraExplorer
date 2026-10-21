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
- text: The Product creates the requested standalone file copies.
  kind: product
  entities:
  - entity: file
    effect: creates
    facts:
    - Name
    - Path
    - Size
    - Modified
    - Type
    - Content
    - Hidden
    - Read only
    - Preview editing
  actor: user
  contexts: &id001
    desktop:
      place: desktop::files
- text: The Product creates the requested folder copies with their contents.
  kind: product
  entities:
  - entity: folder
    effect: creates
    facts:
    - Name
    - Path
    - Modified
    - Contents
    - Listing status
    - Hidden
    - Sort order
  actor: user
  contexts: *id001
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

# Copy into another folder

## Trigger

The person drops paths with a copy effect.

## Outcome

Copies of the selected file and folder contents are created at the destination through Windows Shell and the destination listing is refreshed.

## Edge cases

- The drop effect respects the source’s allowed operations.
- By default, a same-volume drop moves and a cross-volume drop copies; an explicit Copy choice requests copying.
- Name collisions are resolved by Windows Shell.
