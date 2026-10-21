---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: A changed preference or arrangement reaches its save point, or the ordinary window closes.
  kind: condition
  entities: []
  contexts:
    desktop:
      place: desktop::files
  unattended: true
- text: The workspace saved arrangement and settings are retained; independently changed favorites and mark values are merged with other windows’ saved changes.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
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
  - entity: mark
    effect: reads
    facts:
    - Path
    - Color
    - Note
    - Item kind
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# Persist the working state

## Trigger

A changed preference or arrangement reaches its save point, or the ordinary window closes.

## Outcome

The workspace saved arrangement and settings are retained; independently changed favorites and mark values are merged with other windows’ saved changes.
