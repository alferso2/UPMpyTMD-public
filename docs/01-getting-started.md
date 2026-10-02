# 1. Getting started

## Requirements

- Python **3.13** (check with `python --version` or `py -3.13 --version`)
- A modern browser (Chrome or Edge recommended — they support the native "Save As" dialog used by *Save session*)
- Access to the UPMpyTMD source repository

The application runs entirely on your own machine: the browser talks to a local Python server at `http://localhost:8000`. No TMD data leaves your computer.

## Install (one time only)

A virtual environment (`.venv`) keeps the packages UPMpyTMD needs separate from anything else installed on your machine. From the repository root:

**PowerShell (Windows)**

```powershell
py -3.13 -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

**cmd.exe (Windows)**

```bat
py -3.13 -m venv .venv
.venv\Scripts\activate.bat
python -m pip install -r requirements.txt
```

**bash (Git Bash, macOS, Linux)**

```bash
python3.13 -m venv .venv
source .venv/Scripts/activate   # macOS/Linux: source .venv/bin/activate
python -m pip install -r requirements.txt
```

To leave the environment run `deactivate`. If `requirements.txt` changes a lot, delete `.venv` and repeat these steps.

## Run

```powershell
.venv\Scripts\Activate.ps1
python run.py
```

`run.py` starts the server and opens `http://localhost:8000` in your default browser. On a headless machine, or if you prefer not to auto-open a browser:

```powershell
python -m uvicorn backend.main:app --reload --port 8000
```

> Do not open `index.html` directly or serve it with `python -m http.server` — reading TMD (HDF5) files requires the Python API.

## First workspace

1. **Add TMD cases** on the upload screen and give each case a short name (it is used everywhere: tables, legends, report captions).
2. **Choose the groups workbook** (see [Input files](02-input-files.md)).
3. For each case, check the **temperature unit** the TMD stores (°C by default) and which **conductor couplings** to read (see [Loading cases](03-loading-cases.md)).
4. Press **Save cases and continue**. A progress bar shows each file as it loads.
5. Start with the [Check](04-check.md) tab to confirm the cases and the group definition are what you expect, then move on to the analysis tabs.

The upload panel can be collapsed from the header once a workspace is loaded, to give the analysis views more room.
