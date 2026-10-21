---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Close the chosen contexts.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace releases the closed contexts and remembers existing closed directory paths; closing the last context closes its window.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Open tabs
    - Closed folders
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Tabs.cs
---

# Close a folder context

## Trigger

The person closes a tab or the other tabs.

## Outcome

The workspace releases the closed contexts and remembers existing closed folder paths; closing the last context closes its window.

## Edge cases

- Closing waits for accepted transfers and the normal preview save path.
