---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Enter the new name.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The file or folder receives its new name and path; its mark and descendant mark paths follow the rename and the location is refreshed.
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Name
    - Path
  - entity: folder
    effect: changes
    facts:
    - Name
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

# Rename one item

## Trigger

Exactly one filesystem item is selected.

## Outcome

The file or folder receives its new name and path; its mark and descendant mark paths follow the rename and the location is refreshed.

## Edge cases

- Cancelling or submitting the same name makes no change.
- A selection other than exactly one item is reported.
- Invalid or conflicting names are reported by the file operation.
