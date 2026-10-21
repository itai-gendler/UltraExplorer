---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Try to save the edits.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::preview
- text: The text draft enters conflict, retains the edits and reports that the source changed; the existing file is left intact.
  kind: product
  entities:
  - entity: text-draft
    effect: changes
    facts: []
    from: Modified
    to: Conflict
  - entity: file
    effect: reads
    facts:
    - Content
  actor: user
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/PreviewTextEditSession.cs
---

# Retain edits after a source conflict

## Trigger

Another application changed the source after it was opened.

## Outcome

The text draft enters conflict, retains the edits and reports that the source changed; the existing file is left intact.

## Edge cases

- Other write failures retain the draft and report the error.
- Unencodable text or contents exceeding 2 MiB are not committed.
