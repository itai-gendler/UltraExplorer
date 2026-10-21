---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose another color.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The mark color changes while its note and path remain intact.
  kind: product
  entities:
  - entity: mark
    effect: changes
    facts:
    - Color
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
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/FolderTagProjection.cs
---

# Change an existing color

## Trigger

A path already has a color or note.

## Outcome

The mark color changes while its note and path remain intact.
