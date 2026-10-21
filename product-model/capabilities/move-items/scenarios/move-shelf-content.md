---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose a destination for the kept content.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::shelf
- text: The Product reads the shelf item path and moves the referenced file to its requested destination.
  kind: product
  actor: user
  entities:
  - entity: shelf-item
    effect: reads
    facts:
    - Path
    - Storage
  - entity: file
    effect: changes
    facts:
    - Path
  contexts:
    desktop:
      place: desktop::shelf
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Controls/DropShelf.xaml.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Controls/ShelfBoard.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# Move kept content to a location

## Trigger

The shelf has an item to use in a destination.

## Outcome

The referenced content is moved to the destination through the ordinary destination handling.

## Edge cases

- A kept directory is moved with its contents.
- A shelf-owned copy is independent of the original temporary source.
