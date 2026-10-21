---
kind: primary
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

# Paste a copy payload

## Trigger

The clipboard contains paths prepared for copying.

## Outcome

Copies of the clipboard file and folder paths are created in the target folder and its contents are refreshed.

## Edge cases

- With multiple selected siblings, the target is their common parent; otherwise it is the focused folder or the focused file’s parent.
- An empty or non-file clipboard is reported.
