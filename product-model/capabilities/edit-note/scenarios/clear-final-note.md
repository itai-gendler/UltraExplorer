---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Clear the annotation.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The mark is removed once the last note text is cleared.
  kind: product
  entities:
  - entity: mark
    effect: removes
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

# Clear a note without a color

## Trigger

The annotation has no color.

## Outcome

The mark is removed once the last note text is cleared.
