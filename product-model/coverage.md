---
scope: Core Windows desktop file workflows, optional archives and shelf, picker contracts, shared state and quiet updates.
method: Static source and documentation inspection at d78bb1495783fd5bdae0d23a780b9326664a1016.
covered:
- description: Filesystem navigation, selection, file commands and retained working contexts.
  paths:
  - src/UltraExplorer/ViewModels/
  - src/UltraExplorer/Models/
  - src/UltraExplorer/MainWindow.xaml.cs
  - src/UltraExplorer/MainWindow.Split.cs
  - src/UltraExplorer/MainWindow.Tabs.cs
  - src/UltraExplorer/MainWindow.Selection.cs
  - src/UltraExplorer/MainWindow.Focus.cs
  - src/UltraExplorer/Services/Watch/
- description: Global search and spatial map membership.
  paths:
  - src/UltraExplorer/Services/Search/
  - src/UltraExplorer/MainWindow.SearchMap.cs
- description: Shared marks, favorites and workspace persistence.
  paths:
  - src/UltraExplorer/Services/FolderMarkService.cs
  - src/UltraExplorer/Services/FolderTagProjection.cs
  - src/UltraExplorer/Services/WorkspaceStore.cs
  - src/UltraExplorer/Services/ViewAllWorkspaceStore.cs
  - src/UltraExplorer/MainWindow.Tags.cs
- description: Shell file operations and shelf storage.
  paths:
  - src/UltraExplorer/Services/NativeShellService.cs
  - src/UltraExplorer/Services/ShellFileOperation.cs
  - src/UltraExplorer/Services/ShelfStore.cs
- description: Quick Look editing and archive actions.
  paths:
  - src/UltraExplorer/QuickPreviewWindow.cs
  - src/UltraExplorer/Services/PreviewTextEditSession.cs
  - src/UltraExplorer/Services/Archives/
  - src/UltraExplorer/MainWindow.ArchivePreview.cs
  - src/UltraExplorer/MainWindow.HoverPreview.cs
- description: Picker requests, choices, client state and COM contract.
  paths:
  - src/UltraExplorer/Picker/
  - src/UltraExplorer/MainWindow.Picker.cs
  - src/UltraExplorer/MainWindow.NativeProxy.cs
- description: Quiet update discovery and explicit installation entry.
  paths:
  - src/UltraExplorer/Services/Updates/
  - src/UltraExplorer/MainWindow.Updates.cs
- description: Settings and canvas selection behavior.
  paths:
  - src/UltraExplorer/SettingsWindow.xaml
  - src/UltraExplorer/Controls/NestedCanvas.Selection.cs
- description: Explicit folder-launch and reveal routing, including incoming-window preference.
  paths:
  - src/UltraExplorer/Services/FolderInvocation.cs
  - src/UltraExplorer/Services/ExplorerLaunchRouter.cs
  - src/UltraExplorer/MainWindow.FolderInvocation.cs
- description: Installed Shell action invocation and application fallback actions.
  paths:
  - src/UltraExplorer/MainWindow.ShellMenus.cs
  - src/UltraExplorer/Services/ShellContextMenu.cs
exclusions:
- description: Rendering, typography and shader implementation do not define additional product workflows.
  paths:
  - src/UltraExplorer/Rendering/
  - src/UltraExplorer/Themes/
  - src/UltraExplorer/Converters/
- description: Build, release, fixtures and recording tools are contributor tooling rather than product behavior.
  paths:
  - tests/
  - tools/
  - samples/
  - .github/
  - scripts/setup-preview-tools.ps1
  - scripts/setup-archive-tools.ps1
- description: Diagnostics and performance instrumentation are internal operational records.
  paths:
  - src/UltraExplorer/Infrastructure/CrashReporter.cs
  - src/UltraExplorer/Services/PerfLog.cs
  - src/UltraExplorer/MainWindow.Bench.cs
unmapped:
- description: Tree-only manual node placement and hidden-branch restoration need a separate workflow expansion.
  paths:
  - src/UltraExplorer/ViewModels/ViewAllViewModel.cs
  - src/UltraExplorer/MainWindow.Drag.cs
- description: Device eject and volume-specific commands are peripheral to the mapped workflows.
  paths:
  - src/UltraExplorer/MainWindow.Devices.cs
- description: Detailed preview provider formats and embedded media controls are summarized at the inspection boundary.
  paths:
  - src/UltraExplorer/Controls/NativePreviewHost.cs
  - src/UltraExplorer/Services/DocumentPreviewService.cs
  - src/UltraExplorer/Services/PreviewTools.cs
- description: Explorer frame adoption and native-session arbitration are summarized by the Windows integration preference; their full lifecycle is deferred.
  paths:
  - src/UltraExplorer/Services/ExplorerReplacementCoordinator.cs
  - src/UltraExplorer/Services/ExplorerWindowObserver.cs
  - src/UltraExplorer/Services/NativeExplorerNavigation.cs
- description: Installer distribution and removal workflows are outside this core desktop-use mapping.
  paths:
  - installer/
  - scripts/install.ps1
- description: Shell extension-specific actions are delegated to the installed extensions; individual action contracts are not mapped.
  paths:
  - src/UltraExplorer/Services/ShellContextMenu.cs
- description: Low-level COM customization and callback event combinations beyond choosing paths and client-state clearing are deferred.
  paths:
  - src/UltraExplorer/Picker/Com/
limitations: []
---

# Coverage


