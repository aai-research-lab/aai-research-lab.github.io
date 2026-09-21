---
layout: page
permalink: /software/
title: Software
description: Open-source tools developed at AAI Research Lab
nav: true
nav_order: 1
---

We build the tools our own research needs, and release them for everyone else's. All three are open source under the MIT licence.

---

## FastMDXplora

##### Molecular dynamics from a PDB code to a finished study — in one command.

```bash
fastmdx explore --system 181L
```

A four-character PDB ID is the only input. FastMDXplora fetches T4 lysozyme, parameterises the benzene bound in its cavity, runs the dynamics, analyses the trajectory, works out which residues hold the ligand in place, and writes the whole study up as a PDF.

Or design the study in a browser with `fastmdx gui` — or describe it in a sentence and let the FastMDXplora Agent write it.

It handles a protein on its own, a protein with a ligand, a membrane protein in one of seven bilayers, free energy along a collective variable without writing PLUMED input, a trajectory from GROMACS, Amber, NAMD or LAMMPS, and many systems at once with a comparison report across all of them.

**It refuses rather than guesses.** An ambiguous ligand charge, a protein backwards in its membrane, a free-energy surface that never converged — each stops the run and is named, not papered over. What comes out, you can defend; what you cannot is marked.

**The config is the study; the manifest is the result.** One file describes the whole study and runs unchanged from a laptop to a cluster. Every run leaves a manifest of every phase, artifact, setting and software version, so a run directory is readable by someone who was not there.

```bash
conda create -n fastmdxplora -c conda-forge fastmdxplora
```

[GitHub](https://github.com/aai-research-lab/FastMDXplora) · [Documentation](https://fastmdxplora.readthedocs.io) · [Your first study](https://fastmdxplora.readthedocs.io/en/latest/first_study.html) · [conda-forge](https://anaconda.org/conda-forge/fastmdxplora)

---

## Prothon

##### How different are two protein ensembles — and is the difference real?

```bash
prothon compare --ensembles wild_type.dcd mutant.dcd --topology topology.pdb
```

```
CBCN (reference: ensemble 0)
  ensemble 1: d = 0.2841 (floor 0.0472) — 34/76 residues differ
```

Two numbers, and the second decides whether the first means anything. Split one ensemble in half and compare the halves: the answer is not zero, because a finite sample never reproduces a continuous distribution exactly. That self-distance is the **noise floor** — the smallest difference this much sampling can resolve. Here 0.2841 clears the floor by six times; had it not, Prothon would say so rather than report a small difference.

**It compares what superposition cannot.** Each ensemble is described by local order parameters, so nothing is superposed: the cost is linear in the number of conformations rather than quadratic, and two different molecules — which share no coordinate frame — need only a residue map from a sequence alignment. Mutant against wild type, a simulation against a deposited ensemble, several models ranked against one reference, an ensemble against experimental R<sub>g</sub>, PRE, FRET and ³J.

**It withholds rather than overstates.** Trajectory frames are not independent draws, and a test that assumes they are calls almost every residue different when nothing differs. Prothon estimates the correlation time from the data and permutes contiguous blocks; where there are too few to build a null, it reports the floor and no p-value. The false-positive rate is measured rather than asserted — 8–16% at a nominal 5%, against 99% for the naive test.

```bash
conda create -n prothon -c conda-forge prothon
```

[GitHub](https://github.com/aai-research-lab/Prothon) · [Documentation](https://prothon.readthedocs.io) · [Your first comparison](https://prothon.readthedocs.io/en/latest/getting_started.html) · [Paper](https://doi.org/10.1021/acs.jcim.3c00145) · [conda-forge](https://anaconda.org/conda-forge/prothon)

---

## CalphaEBM

##### A learned energy function for coarse-grained protein dynamics.

CalphaEBM is a physics-based, machine-learned C-alpha energy function that holds the native basin across diverse folds. It splits the effective free energy into four interpretable terms — backbone geometry, Ramachandran basins and hydrogen bonding, tertiary packing, and excluded volume — totalling just 13,032 trainable parameters, all of them producing smooth differentiable forces for Langevin dynamics.

Trained on 2,280 monomeric chains, it keeps native contacts (Q > 0.96) and native compactness (radius of gyration within 2% of the crystal structure) across all 16 validation proteins. On villin headpiece HP35 it held Q = 1.000 over one million sampling steps.

[GitHub](https://github.com/aai-research-lab/CalphaEBM)

---

Work here is supported by the CSUDH Startup Fund and the EFA Faculty Legacy Fund.
