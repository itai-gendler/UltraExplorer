---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose copy to the other pane.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The Product creates the requested standalone file copies.
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
  actor: user
  contexts: &id001
    desktop:
      place: desktop::files
- text: The Product creates the requested folder copies with their contents.
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
  contexts: *id001
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Split.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# Copy to the other pane

## Trigger

Both nested panes are open.

## Outcome

The selected file and folder paths are copied into the other pane’s captured folder after confirming that it is still the destination.

## Edge cases

- If the other pane navigated elsewhere, closed, or its folder is unavailable before the operation begins, nothing is transferred.
- Items already inside the destination are excluded.
