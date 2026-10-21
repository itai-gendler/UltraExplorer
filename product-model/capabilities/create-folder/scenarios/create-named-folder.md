---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Enter a directory name and confirm creation.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The named folder is created and the target contents are refreshed.
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

# Create a named folder

## Trigger

The person has a target directory.

## Outcome

The named folder is created and the target contents are refreshed.

## Edge cases

- Cancelling creates nothing.
- An absent target or rejected name is reported.
