---
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/FolderMarkService.cs
---

# Mark

A path-associated color and note shared by the canvas views and app windows. Tags are the navigation projection of colored folders.

## Information kept

- **Path** — The marked path.
- **Color** — The chosen non-default color, or no color.
- **Note** — The annotation text, independent of the color.
- **Item kind** — Whether the path is known to name a file or folder.
