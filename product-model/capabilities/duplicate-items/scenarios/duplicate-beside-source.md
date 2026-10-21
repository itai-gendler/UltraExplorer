---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Duplicate the selection.
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

# Duplicate selected items

## Trigger

The person requests Duplicate.

## Outcome

A new file or folder copy is created beside each selected source with a distinct destination name, and the parent listings are refreshed.

## Edge cases

- Windows may reject a recursive destination that is too long; the error is reported.
- A cancelled duplication refreshes affected locations.
