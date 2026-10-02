# 12. Thermal report

Build an ESA-style thermal analysis report — outline, prose, tables and figures — directly from the results computed in the other tabs.

## Sections

A flat, indentable outline: add, remove, rename, reorder and nest sections to any depth. A typical thermal analysis report outline is provided as a starting point and can be fully edited.

Each section contains any mix of:

- **Text blocks** — rich text (bold, italic, underline, ordered / bullet lists).
- **Table / figure blocks** — taken from the gallery.

## Gallery

Every **Save to report** button in the app (Check, Group attributes, Group results, Compare groups, Flow explorer, Chart, CSG, Requirements…) adds an item to the gallery immediately, with a default caption describing what was saved. Tables are captured as tables; charts as PNG images. A confirmation appears next to the button that was clicked. Captions are editable afterwards.

You can also **upload your own images** (captioned with the file name by default).

### Refreshing data

Each saved item stores a *recipe* — which computation and parameters produced it — rather than a frozen value. **Refresh data** on an item, or **Refresh all data**, recomputes it against whatever TMD is currently loaded under the same case name.

- Tables are recomputed exactly.
- Chart tab and CSG charts are re-rendered and re-captured.
- Flow explorer charts and Requirements items need to be saved again after loading new data.
- Uploaded images have nothing to refresh.

## Variables

Named values that stay live:

- a group attribute value,
- total / GL-only / GR-only heat flow, or the raw GL/GR coupling, between two groups,
- a GL/GR conductor between two specific nodes.

Insert them into any text block with **Insert variable**; the preview shows the live value with its unit.

## Cross-references

Give any table or figure block a short **label**. **Insert reference** in a text block inserts a reference that the preview resolves to the block's current *Table N* / *Figure N* number, so it stays correct when blocks are added or reordered.

## Preview

**Show preview** renders the whole document with numbered section headings and table/figure captions.

## Versions

- **Save version** freezes the current sections, gallery and variables under a label (the next `N.N` is suggested).
- **Continue from here** on a past version (click twice to confirm, since it replaces unsaved work) starts a new working copy from it and refreshes every saved item against the currently loaded TMDs. Typical use: load the v2.0 TMDs under the same case names, continue from version 1.0, and only revise the prose.
- Past versions remain viewable, read-only.

Everything is stored in the [session file](13-sessions.md); nothing is stored on a server. LaTeX / PDF export is not available yet.
