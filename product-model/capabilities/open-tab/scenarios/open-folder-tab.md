---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Open a new tab.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace adds a separate context, initially at the user profile unless a location was specified, and presents that context.
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

# Open a folder tab

## Trigger

The person requests a new tab.

## Outcome

The workspace adds a separate folder context, initially at the user profile unless a location was specified, and presents that context.
