---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose the desired values.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::optional-settings
- text: The settings retain the chosen values and apply them without a separate Save action.
  kind: product
  entities:
  - entity: settings
    effect: changes
    facts:
    - Archives
    - Shelf
    - Copy path button
  actor: user
  contexts:
    desktop:
      place: desktop::optional-settings
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/SettingsViewModel.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.OptionalFeatures.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Controls/DropShelf.xaml.cs
---

# Change a preference in Optional features

## Trigger

The person changes a preference in this section.

## Outcome

The settings retain the chosen values and apply them without a separate Save action.

## Edge cases

- A preference-save failure is reported.

## Decision points

### Change an optional feature

Which preference changed?

- Archive browsing changed → apply it on the nested canvas; disabling returns out of an archive location. Tree view keeps treating archive files ordinarily.
- Shelf visibility changed → show or hide the collection; hiding preserves its retained entries.
- Copy path button changed → add or remove the optional hover action.
