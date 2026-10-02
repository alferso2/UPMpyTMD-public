# 7. Group results

Transient results for one group at a time, plus a group-comparison tool.

## Summary

- **Transient table** — every attribute at every timestep.
- **Time-aggregated overview** — peak Tmax, lowest Tmin and time-averaged Tmean / Tcw / QA / QE / QS / QI / QR. This is an aggregate over the whole transient, not a snapshot at one instant, and is labelled as such.

## GL / GR

Internal and external conductor breakdowns of the group, each independently hideable:

- Filter to a single node number.
- **High / Low / Zero / Inactive tiles**, driven by the High and Low threshold inputs. Click a tile to list the matching conductors.
- **Group 2 filter** — narrow the external conductors to those connecting the two groups, optionally down to one node on each side.

Each of the three views (internal, external, cross-group) has:

- **Visualize couplings** — a bar chart with every node of the group(s) on the x-axis. Coupled nodes are highlighted, the bar height is the node's total |GL| or |GR|, and hovering names the node(s) it is coupled to with their labels and coupling values. The cross-group chart shows the two groups as side-by-side panels on a shared y-scale.
- **View 3D** — the nodes at their real XYZ positions with a line for every coupled pair. Internal/external views show uncoupled nodes in light grey and coupled ones in amber; the cross-group view shows group 1 in blue, group 2 in grey, and any coupled node in red.

## Compare groups

Builds attribute differences between pairs of groups over time:

1. Choose any number of cases.
2. Add pairs: *Group A + attribute* and *Group B + attribute*. Each attribute can be Tmax, Tmean, Tmin, Tcw, QA, QE, QS, QI or QR. A and B may be the same group — e.g. Tmax − Tmin of one group is its spatial gradient.
3. Choose which reductions to show: **Min**, **Average**, **Max** (all by default; for a steady-state case they are identical, so one is enough).

The result is one table — rows = pair × reduction, with a Unit column; columns = cases. In difference mode, each case's per-pair series is first subtracted from the reference case's at matching times, then reduced.
