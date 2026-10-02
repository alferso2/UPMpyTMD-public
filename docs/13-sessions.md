# 13. Sessions

## Save session

Creates a portable `.upmtmd` file containing:

- the TMD files and the groups workbook,
- case names and per-case settings,
- the state of every analysis tab you opened: case selection, groups and attributes, units, and any list you built (Flow explorer chart types, Compare-groups pairs, I/F interfaces and imported workbook, Requirements table and presets, the complete Thermal report).

In Chrome and Edge, the browser's native **Save As** dialog lets you choose the folder and file name; other browsers download the file to their default download folder. Nothing is stored on a server.

> A session file contains the TMD files themselves. Treat it with the same confidentiality as the model results.

## Import session

1. **Import session** restores the input files and settings on the upload screen.
2. Press **Save cases and continue**. The workspace is loaded and, tab by tab, each saved selection is re-applied and its *Generate* is re-run, so tables and charts come back with fresh data rather than a stale snapshot.
