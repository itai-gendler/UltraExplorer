---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Enter a name pattern.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace filter highlights matching loaded names without rearranging the hierarchy; the current-folder list filters its own rows.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Filter
  - entity: file
    effect: reads
    facts:
    - Name
    - Path
  - entity: folder
    effect: reads
    facts:
    - Name
    - Path
    - Contents
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
  target: src/UltraExplorer/ViewModels/FolderListViewModel.cs
---

# Find names in loaded branches

## Trigger

The person enters a local name or wildcard filter.

## Outcome

The workspace filter highlights matching loaded names without rearranging the hierarchy; the current-folder list filters its own rows.

## Edge cases

- Clearing the pattern restores the ordinary presentation.
- Unvisited branches require global search.
