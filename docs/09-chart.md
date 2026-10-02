# 9. Chart

Interactive time plots, stability analysis and interface temperature gradients. Four subtabs.

## Temperature

Plot any attribute (Tmax, Tmean, Tmin, Tcw, QA, QE, QS, QI, QR, C, A) of any groups on a left axis and, optionally, a second set (its own groups and attributes) on a right axis. Per-case overlay or difference vs. a reference case.

### Reading the chart

Three things can vary at once, so each has its own visual channel:

| Varies | Channel |
|---|---|
| Group | Line colour (the same group keeps its colour across cases and axes) |
| Case | Dash pattern (solid, dash, dot, dash-dot…) |
| Attribute | Opacity (first attribute opaque, each further one more transparent) |

Below the chart, three small legends — **Groups**, **Cases**, **Attributes** — explain each channel; only channels that actually vary get a legend row. A right-axis-only attribute is labelled *(right axis)*. Hover shows the value to 4 significant figures with the full trace name. The downloadable standalone HTML uses Plotly's regular per-trace legend instead.

## Flux

The same plot for heat loads (QA, QE, QS, QI, QR, C, A) on a single axis, plus a **group-to-group heat exchange** plot: conductive (GL) and/or radiative (GR) exchange between two chosen groups over time.

## Stability

- **Spatial stability** — Tmax − Tmin of each group at every timestep.
- **Temporal stability** — per-node ΔT looking back exactly the chosen time window (correct on non-uniform timesteps), shown as a min / mean / max band per group.
- **Temporal stability since t = 0** — per-node ΔT against the initial timestep.

The x-axis runs from 0 to the longest transient among the cases selected for that chart.

## I/F gradient

Temperature gradient across interfaces between two sides (groups or node sets).

### Methods

- **Real conductor pairs** — each side is restricted to the nodes that have an actual GL and/or GR conductor to the other side (selectable). Then
  `ΔT = max(|Tmax(A) − Tmin(B)|, |Tmax(B) − Tmin(A)|)`
  over those coupled nodes, reporting the larger direction and the specific hot / cold nodes.
- **Tmax/Tmin envelope** — the same comparison over each side's *entire* node set, ignoring connectivity.

### Defining interfaces

- **Manually**, with an optional ΔT limit (editable at any time from the interface list).
- Optionally with an **ordered chain of intermediate groups** (source → G1 → G2 → destination) to check indirect couplings: side A is restricted to source nodes coupled to G1, side B to destination nodes coupled to the last intermediate group. The chain only affects *Real conductor pairs*. If an intermediate group has no conductor to the next one, that method has no data and the plot says so.
- **Imported from Excel** — see [Input files](02-input-files.md#interfaces-workbook-optional-if-gradient).

### Results per interface

Each interface is a collapsible block with:

- **GL/GR pairs considered** (Real conductor pairs) — node pair, groups, coupling and value at a chosen time. Hideable, with per-column filters. **Apply filter** recomputes the ΔT using only the nodes left in the filtered pairs; **Reset to all pairs** restores the original. Tables over 2,000 rows are only built when **Show table** is pressed.
- **ΔT(t) chart** overlaid with both sides' Tmean(t).
- **Custom plot** — choose X and Y among time, either side's Tmax / Tmean / Tmin / Tcw, or ΔT. For a single-timestep case the two values are printed instead of plotting a single point.
- **CSV export** of every thermal node at the worst-ΔT instant, for downstream thermo-elastic analysis.

A final **summary table** lists every interface × method with its max ΔT, the time it occurs, its limit and **PASS / FAIL / Not checked**.
