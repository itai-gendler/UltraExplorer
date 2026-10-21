---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Move the tab to another position.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace retains the new order of its open tabs for the current window.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Open tabs
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Tabs.cs
---

# Reorder folder contexts

## Trigger

The person moves a tab.

## Outcome

The workspace retains the new order of its open tabs for the current window.
