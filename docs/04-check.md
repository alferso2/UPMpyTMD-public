# 4. Check

The first tab after loading. Use it to confirm that the cases and the group definition are what you expect before trusting any analysis.

## Case info

Per case: general information, the **Loaded as °C/K** and **Couplings: …** badges, and the list of hierarchy levels (which can be saved to the report).

### Group hierarchy gaps

Per case, the tab flags:

- **Unassigned nodes** — nodes not covered by any group.
- **Parent gaps** — for every group with children, nodes counted in the group but not covered by the union of its children's `ID` definitions. Shown as clickable `missing/total` counts that expand to the exact node list.

A gap is a property of the groups workbook, not a calculation error. It does mean that any feature that splits a group's total into its children will legitimately give a different total once it goes past the level where the gap is, because those nodes are unreachable from the children.

## GL conductors / GR conductors

Reports of the conductive (GL) and radiative (GR) couplings in each case, including a 3D coupling viewer that draws each node at its real XYZ position with a line per coupled pair, and a *highlight longer than* distance input to spot suspiciously long conductors.

## Node explorer

Search nodes by user number or label and inspect their attributes.
