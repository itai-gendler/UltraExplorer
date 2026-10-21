---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Switch to the other tab.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace presents that retained context with its selection, camera, history, search, list and split panes intact.
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

# Return to a retained context

## Trigger

The person chooses another tab.

## Outcome

The workspace presents that retained context with its selection, camera, history, search, list and split panes intact.

## Edge cases

- Holding a file drag over another tab presents its contents so a destination inside it can be chosen; a tab header is not a transfer destination.
