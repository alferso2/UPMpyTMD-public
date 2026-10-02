# 14. Troubleshooting

**A TMD fails to load with an out-of-memory message.**
The message states how much memory the read needed. Reload the case with fewer couplings (*GL only*, *GR only* or *None*) — see [Loading cases](03-loading-cases.md#memory).

**The interface looks outdated after updating the app.**
The server tells the browser to revalidate `index.html` and `assets/*` every time, so a normal reload is enough. If it still looks stale, check you started the server from the updated folder.

**A group's total changes when searching deeper in Flow explorer.**
Usually a hierarchy gap in the groups workbook: some nodes of the parent are not covered by any child. Check the *Group hierarchy gaps* in the [Check](04-check.md) tab.

**A group shows no data / "Not checked".**
Its `ID` specification resolved to zero nodes. Check the node ranges or label substring in the groups workbook (label matching is case-sensitive).

**I/F gradient "Real conductor pairs" has no data.**
The two sides (or two consecutive groups of a chain) have no GL/GR conductor between them, or the case was loaded without the needed couplings.

**Opening `index.html` directly, or serving it with `python -m http.server`, does not work.**
That is expected — the app needs the Python API to read TMD files. Use `python run.py`.
