---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Switch the active pane.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace activates the other pane’s location, selection, history and filter for subsequent commands.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Split
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Split.cs
---

# Work in the other pane

## Trigger

Two panes are open.

## Outcome

The workspace activates the other pane’s location, selection, history and filter for subsequent commands.
