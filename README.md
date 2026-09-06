# openpencil_db

Shared OpenPencil storage. Holds the **design-system library** that the OpenPencil app loads
from a GitHub repository (Storage → GitHub repository → this repo).

## Structure

```
open-pencil/libraries/
  ds.skala-real/
    manifest.json                  # { schemaVersion, summary: { name, latestRevisionId, assetCount } }
    revisions/<revisionId>.json    # serialized ComponentLibraryRevision (encoded Map/Uint8Array)
  ds.skala-real.fig                # human-readable copy of the design-system definitions
open_pencil_storage/               # OpenPencil canvas/document namespace (separate)
```

## Connect in OpenPencil

1. OpenPencil → Settings → Storage → **GitHub repository** → connect to `codenol/openpencil_db`.
2. OpenPencil → AI & agents / Libraries → source **Storage** → libraries appear.
3. Enable the library (`ds.skala-real`) in the Assets panel — components (layout, sidebar,
   menuitem, badge, …) and `icon-*` assets are then available to the AI.

## Update the library

- Library content changes are published/committed to `open-pencil/libraries/ds.skala-real/`.
- Consumers `git pull` (or re-open) to get the latest revision.

## Components

49 assets: layout, sidebar, menu-button, menuitem, label, badge, context-menu-item, input,
dropdown, button, content-main-healthcheck, context-menu, pak-cards, option-switcher,
toggle-button, card-pak + 33 `icon-*` glyphs from `DS_icons`.
