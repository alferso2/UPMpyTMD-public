# 8. Flow explorer

Steady-state conductive (GL) and radiative (GR) heat flow between groups. Results are shown first as a table, then as a chart built from the same data.

## Choosing the groups

- Select source and destination groups directly, or
- Use **Search**: pick one source group and a **maximum hierarchy level** (absolute, relative to the whole group tree). The app checks every group at exactly that level — plus, for branches that end earlier, that branch's deepest group — for a real GL/GR coupling with the source, and keeps only the candidates that actually have one.

## Tolerance

Connectors whose value (in the selected Qunit) is at or below the tolerance are not dropped: per source group they are folded into synthetic **Incoming others** / **Outcoming others** rows, so the total flow is always fully accounted for.

## Chart types

- **Sankey** — one diagram per source group. Each band is coloured like the group at its other end and outlined in black. The value of every band is printed on it, staggered left / centre / right so neighbouring labels do not overlap; group names are drawn outside the bands. Bands too thin to hold text are left unlabelled (hover still works). A full-screen view is available.
- **Bars**
- **Network** — global, circular, or per-source star layout. A legend shows the flux types (Conductive / Radiative / Solar / Earth). Each group is a box sized to its label, showing a chosen temperature attribute (*Network node attribute*: Tmax / Tmean / Tmin / Tcw, Tmean by default). Hover shows the group's external loads.

## Overlapping groups

Flux between two groups whose node sets overlap (a group and one of its ancestors) excludes conductors that are internal to the smaller group. A descendant's flux to its parent therefore equals the sum of its fluxes to each of its siblings, as required by conservation. The same rule applies everywhere group-pair conductors are matched (Chart's group-to-group exchange plot, I/F gradient's *Real conductor pairs* method).

## Save to report

Saves the table, or a PNG of the chart (several Sankey / network panels are stacked into one image).
