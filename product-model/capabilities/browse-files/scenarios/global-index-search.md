---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Enter the global query and choose a result.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace presents matching files and folders with the current location first, then descendants, then other locations; choosing a result reveals it without reshuffling the list for that reveal.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Search
    - Locations
    - Camera
    - Selection
  - entity: file
    effect: reads
    facts:
    - Name
    - Path
    - Size
    - Modified
    - Type
  - entity: folder
    effect: reads
    facts:
    - Name
    - Path
    - Modified
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/SearchViewModel.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Search/SearchEngine.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Search/SearchRanking.cs
---

# Search using Everything

## Trigger

The person enters a global query while Everything has a ready index.

## Outcome

The workspace presents matching files and folders with the current location first, then descendants, then other locations; choosing a result reveals it without reshuffling the list for that reveal.

## Edge cases

- A failed supplementary query keeps the successful main indexed results.
- The displayed set is bounded; counts may exceed the displayed results.
- An empty query clears the search.
