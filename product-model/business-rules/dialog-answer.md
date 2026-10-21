---
appliesTo:
- type: entity
  id: dialog-request
  effect: changes
  to: Accepted
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogSession.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogValidator.cs
permits:
- actors:
  - user
  when:
  - fact: Interaction
    is: true
  - fact: Caller decision
    is: Accepted
---

# Users complete a dialog after required interaction and caller acceptance

A completed choice obeys the request’s interaction requirement and receives the caller’s acceptance. The person can correct a rejected answer while the request remains pending.
