---
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Models/ViewAllGraphModels.cs
---

# Workspace

The working arrangement of filesystem locations. Each retained folder context and each split pane keeps its own navigation state; the ordinary workspace also has saved state for later starts.

## Information kept

- **Locations** — The roots and active path of each working context.
- **Selection** — Selected paths, focus, range anchor and totals for each pane.
- **History** — The backward and forward navigation of each pane.
- **Camera** — The view of each location.
- **Filter** — The local name filter of each pane.
- **Search** — The current global query, result selection and result or map mode.
- **Split** — Whether two independent panes are open and which is active.
- **Open tabs** — The ordered retained folder contexts and the active one.
- **Closed folders** — Recently closed tab paths available to reopen.
- **Saved arrangement** — The stored roots, expanded locations, active paths and camera state.
