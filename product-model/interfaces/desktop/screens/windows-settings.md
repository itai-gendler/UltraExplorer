---
entities:
- entity: settings
  shows: &id001
  - Windows integration
  - Incoming folders
  - Win E
  collects: *id001
- entity: application-exception
  shows:
  - Application
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/SettingsWindow.xaml
---

# Windows Explorer

The Windows Explorer preferences and their current values.
