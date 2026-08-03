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

---

## Prothon

A Python package for efficient comparison of protein conformational ensembles using local order parameters.

Prothon represents an ensemble as a vector of probability distributions over local structural measures, and quantifies dissimilarity between ensembles with a Jensen–Shannon distance metric and statistical significance testing. On ubiquitin ensembles it ran up to 88 times faster than ENCORE while using 48 times fewer computing cores.

**Ensemble representations**

- C-beta contact number (`cbcn`) and C-alpha contact number (`cacn`)
- Virtual C-alpha–C-alpha bond angles (`caba`) and torsion angles (`cata`)
- Solvent accessible surface area (`sasa`)

**Also provides**

- Local (per-residue) and global dissimilarity analysis with significance testing
- Dimensionality reduction — PCA, MDS, and t-SNE — with 2D scatter plots
- Ensemble matrices as CSV, heatmaps, and bar/line dissimilarity plots
- A command-line tool and a Python API, with methods to replot and customise every figure

[GitHub](https://github.com/aai-research-lab/Prothon) · [Paper](https://doi.org/10.1021/acs.jcim.3c00145)

**Citation.** Aina, A., Hsueh, S. C. C. and Plotkin, S. S. _PROTHON: A Local Order Parameter-Based Method for Efficient Comparison of Protein Ensembles._ Journal of Chemical Information and Modeling **63**(11), 3453–3461 (2023). [doi:10.1021/acs.jcim.3c00145](https://doi.org/10.1021/acs.jcim.3c00145)

---

## CalphaEBM

A physics-based, machine-learned protein C-alpha energy function that achieves native basin stability across diverse protein folds.

CalphaEBM decomposes the effective free energy into four interpretable terms, totalling just 13,032 trainable parameters:

| Term                | Parameters | What it captures                                                                                                                                   |
| ------------------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **LocalEnergy**     | 12,226     | Backbone geometry: an 8-residue sliding-window MLP over (θ, φ) angles with learned amino acid embeddings                                           |
| **SecondaryEnergy** | 583        | Ramachandran basin potentials — helix, sheet, PPII, turn — with sequence-dependent mixture weights, plus helical and sheet hydrogen bond distances |
| **PackingEnergy**   | 222        | Tertiary packing: 5-group coordination statistics with product Gaussian scoring                                                                    |
| **RepulsionEnergy** | 1          | Excluded volume: a PDB-derived repulsive wall with differentiable interpolation                                                                    |

Every term produces smooth, differentiable forces suitable for Langevin dynamics (MALA) sampling.

Trained on 2,280 high-quality monomeric protein chains (L = 40–512), the model holds native contacts (Q > 0.96) and native compactness (radius of gyration within 2% of the crystal structure) across all 16 validation proteins, which span a range of lengths and fold classes. On villin headpiece HP35 it maintained Q = 1.000 over one million MALA steps.

[GitHub](https://github.com/aai-research-lab/CalphaEBM)

Developed with support from the EFA Faculty Legacy Fund award _Deep Learning the Energy Landscape of a Coarse-Grained Model of Proteins_.
