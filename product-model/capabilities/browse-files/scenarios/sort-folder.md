---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose an order.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The folder sort order changes in the canvas and list; the configured scope decides whether this affects one location or the default for all locations.
  kind: product
  entities:
  - entity: folder
    effect: changes
    facts:
    - Sort order
  - entity: settings
    effect: reads
    facts:
    - Sorting
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Models/FolderOrders.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/ViewAllViewModel.cs
---

# Order the current folder

## Trigger

The person chooses Name, Date modified, Type or Size and a direction.

## Outcome

The folder sort order changes in the canvas and list; the configured scope decides whether this affects one location or the default for all locations.

## Edge cases

- Individual orders do not propagate into subfolders.
- Switching to all-folder scope retains the individual orders for a later switch back.
