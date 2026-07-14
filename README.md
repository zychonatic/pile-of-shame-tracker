# Pile of Shame Tracker

A single-file webapp to track your miniature-painting backlog.

## Usage

Just open `index.html` in any browser (double-click it). No install, no server, no build.

- **Armies** — add armies in the left sidebar; each shows its finished/total progress.
- **Units** — add units to the selected army with a model count and a painting stage
  (Unassembled → Assembled → Primed → Painting → Based → Finished). Change a unit's stage
  inline from the dropdown.
- **Pile of shame counter** — the top bar shows how many units across all armies are still unfinished.
- **Paint Schemes** — build reusable colorschemes (name, brand/range, role, hex swatch),
  attach a default scheme to an army, and optionally override it per unit.

## Saving your data

- Your data **auto-saves in the browser** (localStorage) on every change, so it's still there
  when you reopen the page.
- Click **Export** to download a dated JSON backup file.
- Click **Import** to load a backup (replaces current data).
- **Reset** clears everything — export first if unsure.

> Note: localStorage is per-browser and per-machine. Use Export/Import to move your pile
> between browsers or devices, and as a real backup.
