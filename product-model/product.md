---
id: ultraexplorer
summary: A native Windows file manager for navigating and working with files on a zoomable map.
category: file-management
tags:
- windows
- file-manager
- filesystem
authors:
- name: So2K
  url: https://github.com/So2K/UltraExplorer
license: MIT
languages:
- en
limitations:
- The supported desktop platform is Windows 11 x64.
- The map represents directory structure rather than storage usage.
- File operations and application launching use Windows Shell and filesystem services.
- Local name filtering covers loaded branches; global discovery depends on directory access or index coverage.
- File dialogs return filesystem paths; applications perform the actual open or save.
references:
- kind: doc
  role: intent
  target: README.md
- kind: doc
  role: intent
  target: CONTRIBUTING.md
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# UltraExplorer

UltraExplorer turns the folder hierarchy into a zoomable map while retaining familiar path navigation, selection and Windows file operations. People find files, work across locations, remember folders with favorites and marks, and inspect content before opening it. Optional integrations bring that navigation to folder launches and supported application file dialogs.

## Intent

“Your files. One zoomable map.” The project aims to make directory structure visible so people can enter a folder and keep their bearings. Contributions should improve a real navigation or file-management workflow while keeping the familiar Windows shell and predictable file operations. Its stated priorities are predictable navigation, selection and file actions, broader removable-drive and offline-path coverage, and clearer search and visual landmarks.
