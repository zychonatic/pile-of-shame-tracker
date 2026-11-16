# Pile of Shame Tracker

A single-file webapp to track your miniature-painting backlog.

## Usage

Just open `index.html` in any browser (double-click it). No install, no server, no build.

- **Armies** — add armies in the left sidebar; each shows its finished/total progress.
- **Units** — add units to the selected army with a model count and a painting stage
  (Unassembled → Assembled → Primed → Painting → Based → Finished). Change a unit's stage
  inline from the dropdown.
- **Pile of shame counter** — the top bar shows how many units across all armies are still unfinished.
- **Paint Schemes** — build reusable colorschemes (name, brand/range, role, hex swatch) as well as
  paint mixes (e.g. 2 parts A + 1 part B, with an approximate blended swatch),
  attach a default scheme to an army, and optionally override it per unit.

## Saving your data

- Your data **auto-saves in the browser** (localStorage) on every change, so it's still there
  when you reopen the page.
- Click **Export** to download a dated JSON backup file.
- Click **Import** to load a backup (replaces current data).
- **Reset** clears everything — export first if unsure.

> Note: localStorage is per-browser and per-machine. Use **Cloud sync** (below) or
> Export/Import to move your pile between browsers or devices.

## Cloud sync across devices (optional)

Each person syncs to a **secret gist in their own GitHub account** — nobody else's data is
visible to you, and yours isn't visible to them.

1. Click **☁ Sync** in the top bar and follow the link to create a GitHub
   *classic* personal access token with **only the `gist` scope** (set an expiration date).
2. Paste the token and click **Connect**. The first device creates a gist named
   `pile-of-shame.json`; other devices using the same token find it automatically.
3. Repeat on each device with the same token.

How it behaves:

- Every change is saved locally right away and pushed to the gist ~2 seconds later.
- When you return to the tab (or come back online) it pulls changes from other devices.
- If this device and another device both changed since the last sync, you're asked which
  version to keep. Choosing the cloud version first downloads this device's version as a
  backup file; choosing this device's version keeps the old cloud version in the gist's
  revision history.
- The token is stored only in that browser's localStorage — only connect on devices you trust.
  A "secret" gist is unlisted, not encrypted: anyone with its URL can read it.
- When the token expires, sync shows an error; disconnect and connect with a new token.
  Your local data is untouched.

### Hosting

Sync also works when opening `index.html` from disk, but for phones it's easiest to host it,
e.g. with GitHub Pages: repo **Settings → Pages → Deploy from a branch → `main` / root**.
