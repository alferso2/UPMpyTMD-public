# 6. Nodes

Per-node attribute table for the chosen groups at a chosen time: T, QA, QE, QS, QI, QR, C, A and the X/Y/Z position. Searchable by user node number or label.

## CSV export

Exports the currently filtered node set with a fixed column layout:

```
NODE, LABEL, X, Y, Z, Time [s], T, QA, QE, QS, QI, QR, C, A
```

X/Y/Z are always written with 6 decimals and T with 3 decimals, so the file can be fed directly into downstream tools (e.g. thermo-elastic mapping).
