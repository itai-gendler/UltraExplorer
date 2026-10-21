---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Reopen the most recently closed location.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The workspace adds a new context for the most recently closed directory path; this restores the location rather than all its old transient state.
  kind: product
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Open tabs
    - Locations
    - Closed folders
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Tabs.cs
---

# Reopen a closed folder

## Trigger

A folder was recently closed in this window.

## Outcome

The workspace adds a new context for the most recently closed folder path; this is a reopened location rather than a recovery of all its old transient state.
