---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose the navigation destination.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace moves to the requested history location or parent; each pane retains its own history.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Locations
    - History
    - Camera
    - Selection
  - entity: folder
    effect: reads
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
  target: src/UltraExplorer/Models/NavigationHistory.cs
---

# Return through navigation history

## Trigger

The person chooses Back, Forward, Up or Home.

## Outcome

The workspace moves to the requested history location or parent; each pane retains its own history.
