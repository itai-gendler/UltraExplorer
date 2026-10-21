---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Open UltraExplorer.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace restores saved roots, expanded locations, active paths, cameras and split state, together with settings and favorites.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Locations
    - Selection
    - Camera
    - Split
    - Saved arrangement
  - entity: settings
    effect: reads
    facts:
    - Canvas
    - Layers
    - Sorting
    - Mouse
    - Archives
    - Shelf
    - Copy path button
    - Windows integration
    - Incoming folders
    - Win E
    - Receive updates
    - Picker registration
  - entity: favorite
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
---

# Resume a saved arrangement

## Trigger

The person starts the ordinary file manager.

## Outcome

The workspace restores saved roots, expanded locations, active paths, cameras and split state, together with settings and favorites.

## Edge cases

- A missing saved state starts with defaults.
- Unreadable state is preserved and its replacement saves are held; a damaged state is set aside when possible before starting afresh.
- A picker keeps a separate arrangement and does not overwrite the ordinary canvas session.
