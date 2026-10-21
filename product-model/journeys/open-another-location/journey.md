---
actors:
- user
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Tabs.cs#NewExplorerTab
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Tabs.cs#SelectTabContext
---

# Work in another location

## Goal

Open another folder context and browse it while keeping the earlier context.

## Success criterion

The new context is usable and the earlier location remains available in its retained tab.
