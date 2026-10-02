# 11. Requirements

Verifies, per group, the worst predicted temperatures across a set of cases against your acceptance limits and margins, and produces a pass/fail summary, a compliance table and a bar chart.

## Inputs

| Control | Meaning |
|---|---|
| **Cases bounding the requirement** | The cases searched for the worst value (e.g. hot + cold). All by default. |
| **Groups** | Groups to verify. Level 1 groups by default. |
| **Tunit** | Display unit for limits and results. |
| **Metric** | *Worst (Tmax/Tmin)* — hottest/coldest single node at any instant (default). *Average (Tmean)* — highest/lowest group mean temperature. |

Press **Load groups into table** to create one row per selected group. Values already entered for groups that remain selected are kept.

### Requirement table

| Column | Meaning |
|---|---|
| Tmin req | Cold acceptance limit |
| Tmax req | Hot acceptance limit |
| Margin cold | Margin subtracted from the worst cold value |
| Margin hot | Margin added to the worst hot value |
| Spatial ΔT req | Limit on the group's largest Tmax(t) − Tmin(t) at one instant |
| Spatial margin | Margin added to the worst spatial ΔT |

A blank margin counts as 0. A blank limit means that check is **Not checked**.

## How it is evaluated

For each group, the worst value is taken over **all selected cases and their full transient**:

| Check | Worst value | Pass if |
|---|---|---|
| Hot | highest Tmax (or Tmean) | worst + margin hot ≤ Tmax req |
| Cold | lowest Tmin (or Tmean) | worst − margin cold ≥ Tmin req |
| Spatial | highest Tmax(t) − Tmin(t) | worst + spatial margin ≤ Spatial ΔT req |

Comparisons are inclusive (a value equal to the limit passes). Spatial ΔT is always node-based, regardless of the Metric. A group with no data is *Not checked*.

## Outputs

- **Summary** — one row per check with a limit: unit, requirement (e.g. `Tmax ≤ 60 °C (hot)`) and Pass/Fail.
- **Compliance** — one row per group with, for each check, the worst value, the case, node and time where it occurs, the margined value, the limit and the status.
- **Bar chart** — margined hot, cold and spatial values per group; green = pass, red = fail, grey = not checked.

Each output has CSV download and **Save to report**.

## Presets

Save the current table (cases, groups, unit, metric and all values) under a name — e.g. *Operational*, *Non-operational* — and load it later. Loading a preset does not compute automatically; press **Compute**.

## Current limitations

- No time window: the whole transient is always searched.
- One set of limits per group for all selected cases.
- Requirement types are limited to hot, cold and spatial ΔT.
- Saved Requirements items in the Thermal report are snapshots: re-run **Compute** and save again to update them.
