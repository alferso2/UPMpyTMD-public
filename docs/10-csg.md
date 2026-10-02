# 10. CSG

ESATAN's per-node stability time constant:

```
CSG = C / ΣGL
```

a node's thermal capacitance divided by the sum of its active linear (GL) conductances. The smallest CSG in the network bounds the maximum stable explicit time step.

CSG is computed only for **diffusive nodes with at least one active GL conductor**; boundary nodes and isolated diffusive nodes are excluded, so they never appear as a spurious CSGmin of zero.

CSG is **not** computed when a case is loaded — only here, for one timestep, when **Generate chart** is pressed.

## Output

Per case:

- A grouped **bar chart** on a log-scale y-axis — one min / mean / max cluster per group, as ESATAN plots it. Tick labels show real values (`20`, `50`, `1000`); the chart grows with the number of groups.
- The underlying **table**.

## CSG threshold

Optional. Adds, per group, a clickable `below/total` count of nodes with CSG below the threshold (e.g. `4/60`), which expands to the matching nodes (with CSV export). Each tile is filled as a gauge in proportion to that fraction, with the percentage next to the group name, so the worst groups stand out.

## 3D heat map

Open any group as a 3D view of its nodes at their real XYZ positions, coloured from red (smallest CSG, least stable) to green (largest). Options:

- **Lower / upper bound** — restrict the colour range; nodes outside it are grey.
- **Log10 colour scale** (requires a positive lower bound) — for CSG spanning several orders of magnitude. Colour-bar labels still show plain CSG values.
