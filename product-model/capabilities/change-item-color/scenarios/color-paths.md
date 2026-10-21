---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose a color.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: Each mark keeps the chosen color and item kind; colored folders appear in Tags while any existing note is preserved.
  kind: product
  entities:
  - entity: mark
    effect: creates
    facts:
    - Path
    - Color
    - Note
    - Item kind
  - entity: folder
    effect: reads
    facts:
    - Name
    - Path
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

# Color selected paths

## Trigger

The person chooses a color for selected paths.

## Outcome

Each mark keeps the chosen color and item kind; colored folders appear in Tags while any existing note is preserved.

## Edge cases

- Changing an existing color updates the same path-associated mark.
- Tag ordering groups colors then names; duplicate names include a parent-location hint.
