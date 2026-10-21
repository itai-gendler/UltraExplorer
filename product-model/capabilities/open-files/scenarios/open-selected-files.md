---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Open the selection.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The selected files are handed to their default applications; selecting a single folder instead navigates into it.
  kind: product
  entities:
  - entity: file
    effect: reads
    facts:
    - Name
    - Path
    - Size
    - Modified
    - Type
    - Content
    - Hidden
    - Read only
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
  - entity: workspace
    effect: changes
    facts:
    - Locations
    - Camera
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# Open the selected files

## Trigger

The person chooses Open.

## Outcome

The selected files are handed to their default applications; selecting a single folder instead navigates into it.

## Edge cases

- Opening more than fifteen ordinary selected files asks for confirmation.
- Application-launch failures are reported.
