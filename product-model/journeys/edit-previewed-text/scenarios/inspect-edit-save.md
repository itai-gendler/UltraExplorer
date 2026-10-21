---
kind: primary
result: achieved
routes:
  desktop: Windows desktop
steps:
- text: The user opens a file for inspection.
  kind: actor
  entities:
  - entity: file
    effect: reads
    facts: &id001
    - Name
    - Path
    - Size
    - Modified
    - Type
    - Content
    - Hidden
    - Read only
  actor: user
  contexts:
    desktop:
      place: desktop::files
  capability: open-preview
- text: The Product presents the file in Quick Look.
  kind: product
  entities:
  - entity: file
    effect: reads
    facts: *id001
  actor: user
  contexts:
    desktop:
      place: desktop::preview
  capability: open-preview
- text: The user changes the text.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::preview
  capability: edit-text
- text: The Product keeps a text draft.
  kind: product
  entities:
  - entity: text-draft
    effect: creates
    facts:
    - Source
    - Text
    - Encoding
    to: Modified
  actor: user
  contexts:
    desktop:
      place: desktop::preview
  capability: edit-text
- text: The user saves the edit.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::preview
  capability: save-text
- text: The file receives the edited contents and the text draft is saved.
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
    - Size
    - Modified
  - entity: text-draft
    effect: changes
    facts:
    - Text
    from: Modified
    to: Saved
  actor: user
  contexts:
    desktop:
      place: desktop::preview
  capability: save-text
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/PreviewTextEditSession.cs
---

# Inspect, edit and save text

## Trigger

The person opens Quick Look on editable text.

## Outcome

The source file contains the saved edits.
