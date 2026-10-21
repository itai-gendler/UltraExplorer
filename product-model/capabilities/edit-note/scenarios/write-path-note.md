---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Enter and save the note.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The mark retains the supplied note independently of its color.
  kind: product
  entities:
  - entity: mark
    effect: changes
    facts:
    - Note
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/ViewAllViewModel.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/FolderMarkService.cs
---

# Write a path note

## Trigger

The person edits a note.

## Outcome

The mark retains the supplied note independently of its color.

## Edge cases

- An empty note clears the annotation.
- Cancelling leaves the existing note unchanged.
