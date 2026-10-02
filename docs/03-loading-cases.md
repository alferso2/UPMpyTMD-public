# 3. Loading cases

## Per-case options

Each case card on the upload screen has:

- **Case name** — short, unique; used in every table, legend and report caption.
- **Temperature unit** — the unit the TMD's raw temperatures are stored in: **°C** (default) or **K**. Can be set per case or for all cases at once. This is the *source* unit used by every physical calculation; the `Tunit` selectors in the analysis tabs are display-only.
- **Conductor couplings** — which conductors to read:

  | Option | Reads | Use when |
  |---|---|---|
  | All | GL and GR | You need both (default) |
  | GL only | Conductive couplings | Radiative network not needed |
  | GR only | Radiative couplings | Conductive network not needed |
  | None | Node attributes only | Only temperatures / heat loads are needed |

  Reading fewer couplings makes large models load much faster and use much less memory (see below).

The Check tab shows a "Loaded as °C/K" and a "Couplings: …" badge per case to confirm these choices.

## Progress

Files are uploaded and parsed one at a time. The progress bar tracks real work inside each file — node attributes, then GL conductors, then GR conductors — with the current timestep, phase and an estimated time remaining, for example:

```
GR conductors: timestep 340/865 (62%) — ~45s left
```

Each finished file is announced as `TMD "<name>" loaded successfully (i/N)`.

If one file of a batch fails, the files that already finished stay loaded (marked **Already loaded**). Fix the failing file and submit again: only the remaining files are retried.

## Adding cases later

Once a workspace is loaded, add more TMD files and press **Add new cases**. Only the new files are read; loaded cases keep their data, and their names and settings become read-only.

## Memory

A conductor block is read as two `timesteps × conductors` arrays of 64-bit floats, so a long transient over a large radiative network can need far more RAM than the file size on disk. If a read runs out of memory, the upload says how much memory it would have needed and which coupling option to choose instead. Choosing *GL only* or *None* is usually enough to load the case.
