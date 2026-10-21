---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Choose the default color for an annotated path.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::files
- text: The mark color is cleared while its existing note remains.
  kind: product
  actor: user
  entities:
  - entity: mark
    effect: changes
    facts:
    - Color
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/ViewAllViewModel.cs#ApplyAccent
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/FolderMarkService.cs#SetAccent
---

# Clear a color while retaining a note

## Trigger

The person restores the default color for a path with a note.

## Outcome

The note remains and the path no longer has a custom color.
