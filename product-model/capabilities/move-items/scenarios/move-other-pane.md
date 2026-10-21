---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose move to the other pane.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The selected file and folder paths are moved into the other pane’s captured folder after confirming that it is still the destination.
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Path
  - entity: folder
    effect: changes
    facts:
    - Path
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Split.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# Move to the other pane

## Trigger

Both nested panes are open.

## Outcome

The selected file and folder paths are moved into the other pane’s captured folder after confirming that it is still the destination.

## Edge cases

- If the other pane navigated elsewhere, closed, or its folder is unavailable before the operation begins, nothing is transferred.
- Items already inside the destination are excluded.
