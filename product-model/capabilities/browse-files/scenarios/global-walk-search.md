---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Enter a query supported by local name matching.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace shows results as a background walk progresses, starting at the current location and then ready fixed drives, and identifies the fallback source.
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
  target: src/UltraExplorer/ViewModels/SearchViewModel.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Search/SearchEngine.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Search/FolderWalk.cs
---

# Search without a ready index

## Trigger

The person searches while the index cannot answer.

## Outcome

The workspace shows results as a background walk progresses, starting at the current location and then ready fixed drives, and identifies the fallback source.

## Edge cases

- The walk stops at 1,500 matches.
- If Everything becomes ready after startup or indexing, the open search can run again against its index.
- Moving to another folder while a walk runs reorders its results for that folder instead of starting over; a walk that reached its limit runs again from the new folder.
