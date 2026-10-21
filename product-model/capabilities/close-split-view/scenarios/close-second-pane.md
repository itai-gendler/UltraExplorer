---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Close the split view.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace returns to a single pane and retains the remaining context.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Split
    - Locations
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Split.cs
---

# Return to one pane

## Trigger

The person closes the split.

## Outcome

The workspace returns to a single pane and retains the remaining context.
