---
appliesTo:
- type: entity
  id: workspace
  facts:
  - Search
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Search/SearchRanking.cs
---

# Search prefers the current location before other locations

Within current-location, descendant and elsewhere groups, noisy locations rank after ordinary ones; name quality, nearby folders, folder-before-file ordering and depth refine the result order.
