# 2. Input files

## TMD result files

ESATAN TMD files (HDF5). Each file becomes one **case**. Several cases can be loaded together (e.g. hot and cold, or two model versions) and compared in every tab.

## Groups workbook (required)

An Excel workbook (`.xlsx`) that defines the groups of thermal nodes used by every analysis. Only the **first sheet** is read; header names are trimmed of surrounding spaces.

| Column | Required | Meaning |
|---|---|---|
| `Level` | yes | Numeric hierarchy level. Level 1 groups are used as the default selection in several tabs. Rows with a non-numeric level are ignored. |
| `Group` | yes¹ | Group name, as shown in the app. |
| `Parent` | no | Name of the parent group (`Father` is accepted as an alias). Builds the group tree. A blank, unknown or self-referencing parent makes the group a root. |
| `ID` | no² | Which nodes belong to the group (see syntax below). |

¹ If there is no `Group` column, `Label`, `Name` or `ID` is used as the name, in that order.
² If there is no `ID` column, `Range` is used; if neither exists, the group name itself is used as the node specification.

### Node specification syntax (`ID` / `Range`)

- **Node-number ranges** — any text containing `#`. After removing the `#`, comma-separated pieces are either an inclusive range `start-end` or a single node number. Only node numbers that exist in the model are kept.
  - `#100-199`
  - `#100-199,300-310`
  - `#5001`
- **Label substring** — any other text is matched (case-sensitive) as a substring of each node's label. `TA_M1` selects every node whose label contains `TA_M1`.
- An empty cell gives an empty group.

### Hierarchy

The tree shown in the app (indentation in group selectors) comes from the `Parent` column, not from `Level`. Group names should be unique; if a name is repeated, the first occurrence is used in the tree and the last one defines its nodes.

The [Check](04-check.md) tab reports **hierarchy gaps**: nodes not covered by any group, and, for every group with children, nodes of the group not covered by the union of its children. These are gaps in the workbook, not calculation errors — but they matter for any feature that decomposes a group into its children (e.g. Flow explorer's *max level to search*).

### Example

| Level | Group | Parent | ID |
|---|---|---|---|
| 1 | PLM | | `#1-99999` |
| 2 | TELESCOPE | PLM | `#1000-4999` |
| 3 | M1 | TELESCOPE | `M1_` |
| 3 | M2 | TELESCOPE | `M2_` |
| 2 | OPTICAL_BENCH | PLM | `#5000-6999` |

## Interfaces workbook (optional, I/F gradient)

Imported from the [I/F gradient](09-chart.md#if-gradient) subtab via **Import Excel (Unit A, Nodes A, Unit B, Nodes B)**. First sheet, one interface per row.

| Column | Meaning |
|---|---|
| `Unit A` | Name of side A (used only for the interface label) |
| `Nodes A` | Node specification for side A — same syntax as the groups `ID` column |
| `Unit B` | Name of side B |
| `Nodes B` | Node specification for side B |

Each row is labelled `"<Unit A> - <Unit B>"`. ΔT limits and intermediate-group chains are not read from the workbook; they can only be defined for interfaces added manually in the app. Imported interfaces are added to the manually defined ones.
