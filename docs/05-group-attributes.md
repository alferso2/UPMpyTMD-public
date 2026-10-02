# 5. Group attributes

Per-group temperatures and heat loads **at one chosen time**.

## Attributes

| Attribute | Meaning |
|---|---|
| Tmax / Tmin | Hottest / coldest node of the group |
| Tmean | Arithmetic mean temperature of the group's nodes |
| Tcw | Capacity-weighted mean temperature, `Σ(Ci·Ti) / ΣCi` |
| QA, QE, QS, QI, QR | Albedo, Earth, solar, internal and residual heat loads (summed) |
| C | Thermal capacitance (summed) |
| A | Area (summed) |

Values match the same-timestamp row of the [Group results](07-group-results.md) transient table exactly — both come from the same per-timestep computation.

## Options

- **Case representation** — show selected cases, or the difference against a reference case.
- **Combine all cases into one table** — one row per group and a two-level column header (case → attribute), instead of one table per case. Works in both representation modes.

## Number formatting

At least 3 decimals, extended for small numbers so that at least 3 significant figures are visible (an area of 0.0023232 m² shows as `0.00232`; 45.238232 °C shows as `45.238`).

## Export

- **Download CSV**
- **Download fancy Excel** — a styled `.xlsx`: bold light-blue headers merged across each case's columns, thin borders and a 3-colour heat map per attribute.
- **Save to report**
