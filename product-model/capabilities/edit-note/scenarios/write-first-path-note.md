---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Write the annotation.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: A mark is created with the path and supplied note, without adding a color.
  kind: product
  entities:
  - entity: mark
    effect: creates
    facts:
    - Path
    - Color
    - Note
    - Item kind
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/ViewAllViewModel.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/FolderMarkService.cs
---

# Write the first annotation

## Trigger

A path has no existing annotation.

## Outcome

A mark is created with the path and supplied note, without adding a color.
