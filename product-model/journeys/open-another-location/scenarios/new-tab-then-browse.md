---
kind: primary
result: achieved
routes:
  desktop: Windows desktop
steps:
- text: The user requests another retained location.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::files
  capability: open-tab
- text: The Product presents the new workspace context.
  kind: product
  actor: user
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Open tabs
    - Locations
  contexts:
    desktop:
      place: desktop::files
  capability: open-tab
- text: The user navigates within the new location.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::files
  capability: browse-files
- text: The workspace presents the chosen folder contents while the earlier context remains retained.
  kind: product
  actor: user
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Locations
    - Camera
    - History
  - entity: folder
    effect: reads
    facts:
    - Path
    - Contents
    - Listing status
  contexts:
    desktop:
      place: desktop::files
  capability: browse-files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Tabs.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/ViewAllViewModel.cs
---

# Open another context and browse

## Trigger

The person requests an additional retained context.

## Outcome

The new location is being browsed and the original context remains available.
