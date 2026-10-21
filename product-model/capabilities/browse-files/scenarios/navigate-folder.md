---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose a location.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace reaches the requested folder, presents its contents and records the navigation in that pane.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Locations
    - Camera
    - History
    - Selection
  - entity: folder
    effect: reads
    facts:
    - Name
    - Path
    - Modified
    - Contents
    - Listing status
    - Hidden
    - Sort order
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/ViewAllViewModel.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/AddressBarViewModel.cs
---

# Navigate to a folder

## Trigger

The person opens a drive, folder, breadcrumb or typed path.

## Outcome

The workspace reaches the requested folder, presents its contents and records the navigation in that pane.

## Edge cases

- A file path reveals its containing location and the named file.
- An unavailable drive or missing path is reported; exact favorite and tag navigation preserves the existing selection when the requested location is unavailable.
- A later navigation supersedes an earlier unfinished request within the same pane.
