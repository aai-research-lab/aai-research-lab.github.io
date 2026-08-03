---
layout: page
permalink: /software/
title: Software
description: Open-source tools developed at AAI Research Lab
nav: true
nav_order: 1
---

## FastMDXplora

**F**ully **A**utomated **Sy**s**T**em for **M**olecular **D**ynamics e**Xplora**tion

FastMDXplora explores a protein's behaviour end to end from a single command. Given a structure — or just a PDB ID — it carries out molecular dynamics exploration through setup, simulation, analysis, and reporting, and hands back publication-ready results.

```
setup  →  simulation  →  analysis  →  report
```

| Phase          | What it does                                                                                                                       |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| **setup**      | Cleans up the structure and builds a simulation-ready system: fixes missing atoms, adds hydrogens, solvates, and adds ions.        |
| **simulation** | Runs the molecular dynamics — energy minimization, equilibration, and production — with optional enhanced sampling.                |
| **analysis**   | Computes standard structural and dynamic metrics, and protein–ligand metrics where a ligand is present, with figures ready to use. |
| **report**     | Packages everything into a slide deck, a written report, and a self-contained bundle you can share.                                |

**Highlights**

- Explore a protein's full dynamics with one command, covering setup, simulation, analysis, and reporting
- Build a protein–ligand system from a PDB identifier alone: the ligand is identified, its chemistry retrieved, and its protonation settled in the binding site — with a refusal rather than a guess where the structure is ambiguous
- Probe protein–ligand binding automatically, with analyses for pose stability, contacts, and hydrogen bonds
- Reach beyond plain MD with built-in PLUMED enhanced sampling: metadynamics, umbrella sampling, steered MD
- Design, start, watch, and review an exploration from a browser, with a 3D viewer and live telemetry
- Scale from a quick single-protein exploration to large parallel campaigns, driven the same way from the CLI or the Python API

**Install**

```bash
pip install fastmdxplora
```

Analysis and reporting are pure pip. Setup and simulation additionally require OpenMM and PDBFixer from conda-forge — see the [installation guide](https://fastmdxplora.readthedocs.io/en/latest/installation.html).

[GitHub](https://github.com/aai-research-lab/FastMDXplora) · [Documentation](https://fastmdxplora.readthedocs.io) · [PyPI](https://pypi.org/project/fastmdxplora/) · MIT licence

**Citation.** The foundational methodology is described in:

Aina, A. and Kwan, D. _FastMDAnalysis: Software for Automated Analysis of Molecular Dynamics Trajectories._ Journal of Computational Chemistry **47**(8), e70350 (2026). [doi:10.1002/jcc.70350](https://doi.org/10.1002/jcc.70350)

A further publication describing FastMDXplora is in preparation.
