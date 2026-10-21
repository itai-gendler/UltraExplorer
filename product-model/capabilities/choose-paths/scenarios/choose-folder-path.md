---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose the location and confirm the answer.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::picker
- text: The dialog request returns the chosen directory paths, using the current location when appropriate.
  kind: product
  entities:
  - entity: dialog-request
    effect: changes
    facts:
    - Filename
    - File types
    - Result paths
    - Caller decision
    - Interaction
    from: Pending
    to: Accepted
  actor: user
  contexts:
    desktop:
      place: desktop::picker
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Picker.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogSession.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogValidator.cs
---

# Choose a folder

## Trigger

A folder request is pending.

## Outcome

The dialog request returns the selected folder paths, using the current location when appropriate.

## Edge cases

- The caller’s multi-selection and type requirements determine which choices are accepted.
- Typing a directory path navigates into it.

## Decision points

### Remember this caller

Does the request identify a client and allow remembered choices?

- Identified client with remembering enabled → keep the last accepted location, type and recent names.
- No client identity or remembering disabled → finish without changing remembered client choices.
