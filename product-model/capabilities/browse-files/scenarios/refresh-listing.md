---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Request a fresh listing.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The folder contents and listing status are refreshed; surviving selected paths remain selected in the workspace.
  kind: product
  entities:
  - entity: folder
    effect: changes
    facts:
    - Contents
    - Listing status
  - entity: workspace
    effect: changes
    facts:
    - Selection
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/ViewAllViewModel.cs
---

# Refresh a location

## Trigger

The person refreshes a location or asks to load more of a capped tree listing.

## Outcome

The folder contents and listing status are refreshed; surviving selected paths remain selected in the workspace.

## Edge cases

- A listing failure is distinguished from an empty directory.
