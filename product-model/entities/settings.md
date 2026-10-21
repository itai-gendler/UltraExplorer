---
singleton: true
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Models/WorkspaceState.cs
---

# Settings

Preferences kept in the current Windows user profile and shared where the product uses a common preference store.

## Information kept

- **Canvas** — Nested or Tree view, favorite shortcuts, split direction, renderer and minimap preference.
- **Layers** — Visibility of files, icons, details, counts, marks, hidden items and hover previews.
- **Sorting** — Default order, per-folder or all-folder scope, and fill order.
- **Mouse** — Whether an empty-space left drag selects or pans.
- **Archives** — Whether archive browsing is enabled; initially off.
- **Shelf** — Whether the drop shelf is shown; initially off.
- **Copy path button** — Whether hover copy-path buttons are shown; initially off.
- **Windows integration** — Whether supported folder and file-dialog integration is enabled; initially off.
- **Incoming folders** — Separate window or a new tab in an available window.
- **Win E** — Whether Win+E opens UltraExplorer independently of general integration; initially off.
- **Receive updates** — Whether quiet update discovery and downloading are enabled; initially on.
- **Picker registration** — Whether the current user has registered UltraExplorer COM picker classes.
