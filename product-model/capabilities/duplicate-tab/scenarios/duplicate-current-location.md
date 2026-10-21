---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Duplicate the tab.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace creates another independent context at the same current location.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Open tabs
    - Locations
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Tabs.cs
---

# Duplicate the current location

## Trigger

The person duplicates a tab.

## Outcome

The workspace creates another independent context at the same current folder.
