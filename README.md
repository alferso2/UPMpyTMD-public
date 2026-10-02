# UPMpyTMD

**Post-processing of ESATAN TMD thermal results — Universidad Politécnica de Madrid**

![Version](https://img.shields.io/badge/version-0.1-blue) ![Python](https://img.shields.io/badge/python-3.13-blue) ![Access](https://img.shields.io/badge/source-on%20request-lightgrey)

UPMpyTMD is a local web application that turns ESATAN TMD result files into the tables, plots and checks a spacecraft thermal analysis needs — without writing post-processing scripts. Load one or more cases (e.g. hot and cold), define node groups in an Excel workbook, and explore temperatures, heat loads, conductive and radiative heat flow, interface gradients, numerical stability and requirement compliance; then assemble the results into a thermal analysis report.

Everything runs on your own machine: model data never leaves it.

## Features

- **Model checks** — case information, group-hierarchy gaps, GL/GR conductor reports and a 3D coupling viewer.
- **Group attributes** — Tmax, Tmin, Tmean, capacity-weighted Tcw and heat loads (QA, QE, QS, QI, QR) per group, per case or as differences against a reference case, with CSV and styled Excel export.
- **Transient results** — time-series tables, time-aggregated overviews and conductor breakdowns per group; attribute differences between any pair of groups.
- **Heat-flow explorer** — conductive and radiative flow between groups as tables, Sankey, bar and network diagrams, with heat-flow conservation across nested groups.
- **Charts** — temperature and flux time plots with multi-case overlays, spatial and temporal stability, group-to-group heat exchange.
- **Interface gradients** — ΔT across interfaces using real conductor pairs or Tmax/Tmin envelopes, including chains of intermediate groups, limits with PASS/FAIL, and node exports for thermo-elastic analysis.
- **CSG** — ESATAN's stability time constant `C / ΣGL` per group, with threshold counts and a 3D heat map.
- **Requirements** — hot, cold and spatial-ΔT verification with margins across bounding cases.
- **Thermal report** — section outline, rich text, live tables, figures and variables, cross-references and versions.
- **Sessions** — the complete workspace in a single portable file.

## Documentation

**[User manual](docs/README.md)** — installation, input file formats and a guide to every tab.

## Access to the software

The source code is hosted in a private repository and access is granted on request — typically to research groups, students and industrial partners working on spacecraft thermal analysis.

To request access, **[open an access request](https://github.com/alferso2/UPMpyTMD-public/issues/new?template=access-request.yml)** with your name, institution and intended use. Access is granted by adding your GitHub account as a collaborator of the private repository.

## Citation

If you use UPMpyTMD in your work, please cite it — see [CITATION.cff](CITATION.cff) or the *Cite this repository* button on this page.

## Author

Alejandro José Fernández Soler — Universidad Politécnica de Madrid (UPM)

## Notices

ESATAN is a trademark of its respective owner. UPMpyTMD is an independent tool and is not affiliated with or endorsed by the ESATAN developers.

The documentation in this repository is licensed under [CC BY 4.0](LICENSE.md). The UPMpyTMD software is not distributed through this repository.
