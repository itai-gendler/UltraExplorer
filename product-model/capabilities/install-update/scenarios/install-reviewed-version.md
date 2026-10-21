---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Open the offered release and explicitly choose installation.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The update enters installing after the person reviews and confirms its version.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts: []
    from: Ready
    to: Installing
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Updates.cs
---

# Install the reviewed version

## Trigger

A ready release has been offered.

## Outcome

The update enters installing after the person reviews and confirms its version.

## Edge cases

- If the offered version changes during preparation, it is shown for review before another install click.
- An installation that cannot complete restores the ready offer and reports the problem.
