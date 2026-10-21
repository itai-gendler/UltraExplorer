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
- text: The Product reads the shelf item path and creates the requested file copy.
  kind: product
  actor: user
  entities:
  - entity: shelf-item
    effect: reads
    facts:
    - Path
    - Storage
  - entity: file
    effect: creates
    facts:
    - Name
    - Path
    - Size
    - Modified
    - Type
    - Content
    - Hidden
    - Read only
    - Preview editing
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

# Copy kept content to a location

## Trigger

The shelf has an item to use in a destination.

## Outcome

The referenced content is copied to the destination through the ordinary destination handling; the shelf item stays.

## Edge cases

- A kept directory is copied with its contents.
- A shelf-owned copy is independent of the original temporary source.
