---
kind: primary
routes:
  cli: Interactive command line
steps:
- text: The user requests a picker with a mode and starting location.
  kind: actor
  actor: user
  entities: []
  contexts:
    cli:
      place: command-line
- text: The Product returns the answered dialog request to the command-line invocation.
  kind: product
  actor: user
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

# Request a picker from a shell

## Trigger

The person invokes the documented picker from a shell.

## Outcome

The invocation returns accepted paths, cancellation or an error.
