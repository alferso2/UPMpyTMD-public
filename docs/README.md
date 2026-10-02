# UPMpyTMD — User manual

UPMpyTMD is a local web application for post-processing ESATAN TMD result files: it reads one or more TMD cases, groups their thermal nodes according to an Excel workbook, and turns them into tables, charts, interface checks, requirement verification and a report — without writing post-processing scripts by hand.

## Contents

1. [Getting started](01-getting-started.md) — install, run, first workspace
2. [Input files](02-input-files.md) — TMD cases and the group / interface Excel workbooks
3. [Loading cases](03-loading-cases.md) — units, coupling options, progress and memory
4. [Check](04-check.md) — case info, hierarchy gaps, GL/GR conductors, node explorer
5. [Group attributes](05-group-attributes.md) — per-group temperatures and heat loads at one instant
6. [Nodes](06-nodes.md) — per-node attribute table and CSV export
7. [Group results](07-group-results.md) — transient tables, conductor breakdowns, group comparison
8. [Flow explorer](08-flow-explorer.md) — heat flow between groups: tables, Sankey, bars, networks
9. [Chart](09-chart.md) — temperature / flux plots, stability, I/F gradient
10. [CSG](10-csg.md) — ESATAN stability time constant per node and group
11. [Requirements](11-requirements.md) — Tmax / Tmin / spatial ΔT verification with margins
12. [Thermal report](12-thermal-report.md) — building a report from saved tables and figures
13. [Sessions](13-sessions.md) — saving and restoring a complete workspace
14. [Troubleshooting](14-troubleshooting.md)

## Conventions used throughout the app

- **Display units are display-only.** Every `Tunit` / `Qunit` selector after upload only changes how values are shown. Calculations that need Kelvin (e.g. Stefan–Boltzmann radiative flux) always use the source unit chosen when the case was loaded.
- **Units in headers.** Every column with a physical unit shows it in its header, e.g. `Tmax [°C]`, `A [m²]`.
- **Case representation.** Most tabs can show the selected cases side by side, or as a *difference vs. a reference case*.
- **Loading and errors.** Every Generate / Refresh / Compute action shows "Loading…" while it runs; if it fails, the result area shows the error message instead.
- **Time axes.** Every chart with time on an axis has its own time-unit selector (s / min / h / day).
- **Save to report.** Most results have a "Save to report" button that sends the table or figure to the [Thermal report](12-thermal-report.md) gallery.
