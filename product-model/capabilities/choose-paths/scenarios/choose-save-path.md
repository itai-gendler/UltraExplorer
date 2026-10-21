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
- text: The dialog request returns the proposed save path and selected type after required confirmations; the caller performs the actual save.
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

# Choose a save destination

## Trigger

A Save request is pending.

## Outcome

The dialog request returns the proposed save path and file type after any required overwrite confirmation; the caller performs the actual save.

## Edge cases

- The caller’s type requirements determine which choices are accepted.
- Typing a directory navigates into it where appropriate; typing a wildcard filters the displayed entries.
- A filename without an extension receives the default or selected-type extension for Save; a trailing dot requests no extension.

## Decision points

### Remember this caller

Does the request identify a client and allow remembered choices?

- Identified client with remembering enabled → keep the last accepted location, type and recent names.
- No client identity or remembering disabled → finish without changing remembered client choices.
