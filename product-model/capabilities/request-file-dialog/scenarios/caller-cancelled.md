---
kind: edge
routes:
  cli: Command-line request
  com: COM request
steps:
- text: The calling application supplies the mode, starting location, filename patterns and selection requirements.
  kind: actor
  actor: calling-application
  entities: []
  contexts:
    cli:
      place: command-line
    com:
      place: picker-api
- text: The Product obtains a person’s choice and returns the cancelled answer to the calling application.
  kind: product
  actor: calling-application
  entities:
  - entity: dialog-request
    effect: reads
    facts:
    - Mode
    - Initial location
    - File types
    - Filename
    - Options
    - Application options
    - Result paths
    - Caller decision
    - Interaction
  contexts:
    cli:
      place: command-line
    com:
      place: picker-api
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogCommandLine.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/Com/FileDialogComBase.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogHost.cs
---

# Return a cancelled picker answer

## Trigger

An application requests a choice.

## Outcome

The caller receives a cancelled answer without accepted paths.
