---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Supply the desired name, type and scope criteria and apply them.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace receives the built query and starts the search.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Search
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.SearchMap.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/SearchBuilderViewModel.cs
---

# Build a search query

## Trigger

The person opens the search-query builder.

## Outcome

The workspace receives the built query and starts the search.
