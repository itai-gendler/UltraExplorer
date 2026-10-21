---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Enter a query for the map.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace shows matching files, folders and their containing branches in their existing positions using a search scoped to the displayed roots, independently of the result-list limit.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Search
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
  target: src/UltraExplorer/Services/Search/SearchMapProjectionBuilder.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.SearchMap.cs
---

# Search the map without moving locations

## Trigger

The person selects map mode on the nested canvas.

## Outcome

The workspace shows matching files, folders and their containing branches in their existing positions using a search scoped to the displayed roots, independently of the result-list limit.

## Edge cases

- A filesystem scan retains unreadable or skipped branches as unknown rather than treating them as empty.
- Queries requiring Everything leave the full map visible with an explanation when a complete indexed answer is unavailable.
- Tree view and file-dialog sessions do not offer map search.
