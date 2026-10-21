---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Enter the text filename and confirm creation.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The named file is created in the target folder and passed to its default application; the target listing is refreshed.
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

# Create and open a text file

## Trigger

The person chooses New text file.

## Outcome

The named file is created in the target folder and passed to its default application; the target listing is refreshed.

## Edge cases

- Cancelling creates nothing.
- If the window closes while creation finishes, the follow-up application launch is omitted.
