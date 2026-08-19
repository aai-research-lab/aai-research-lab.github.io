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

Four characters of input. FastMDXplora fetches T4 lysozyme, parameterises the benzene bound in its cavity, runs the dynamics, analyses the trajectory, works out which residues hold the ligand in place, and writes the whole study up as a PDF.

It handles a protein on its own, a protein with a ligand, a membrane protein in one of seven bilayers, free energy along a collective variable without writing PLUMED input, a trajectory from GROMACS or Amber or NAMD, or many systems at once with a comparison report across all of them.

**It refuses rather than guesses.** An ambiguous ligand charge, a protein backwards in its membrane, a free-energy surface that never converged — each stops the run and is named rather than papered over. What comes out, you can defend; what you cannot is marked.

The whole study lives in one config file, reproducible by anyone holding it, and reachable equally from a GUI, the command line, or Python.

[GitHub](https://github.com/aai-research-lab/FastMDXplora) · [Documentation](https://fastmdxplora.readthedocs.io) · [Quick start](https://fastmdxplora.readthedocs.io/en/latest/getting_started.html) · [conda-forge](https://anaconda.org/conda-forge/fastmdxplora)

---

## Prothon

##### How different are two protein ensembles — and is the difference real?

```bash
prothon -traj wild_type.dcd,mutant.dcd -top topology.pdb -m cbcn
```

Prothon describes each ensemble by local order parameters — contact numbers, virtual bond and torsion angles, solvent accessibility — and measures the distance between them. Because the description is local, nothing is superposed. Two things follow.

**It scales linearly, not quadratically.** Methods built on pairwise RMSD must superpose every structure against every other. Prothon never superposes anything, so ensembles of tens of thousands of conformations are ordinary rather than prohibitive.

**It compares molecules that are not the same molecule.** A superposition needs a shared coordinate frame, and a wild type and its mutant do not have one. Local order parameters need only a residue mapping.

**It reports what it cannot resolve.** Two halves of a _single_ ensemble differ slightly, because a finite sample never reproduces a continuous distribution exactly. Prothon measures that floor, prints it beside every result, and calls anything below it unresolvable rather than small. Significance is decided against a permutation null and corrected for multiple testing.

[GitHub](https://github.com/aai-research-lab/Prothon) · [Documentation](https://prothon.readthedocs.io) · [Paper](https://doi.org/10.1021/acs.jcim.3c00145) · [PyPI](https://pypi.org/project/prothon-ensembles/)

---

## CalphaEBM

##### A learned energy function for coarse-grained protein dynamics.

CalphaEBM is a physics-based, machine-learned C-alpha energy function that holds the native basin across diverse folds. It splits the effective free energy into four interpretable terms — backbone geometry, Ramachandran basins and hydrogen bonding, tertiary packing, and excluded volume — totalling just 13,032 trainable parameters, all of them producing smooth differentiable forces for Langevin dynamics.

Trained on 2,280 monomeric chains, it keeps native contacts (Q > 0.96) and native compactness (radius of gyration within 2% of the crystal structure) across all 16 validation proteins. On villin headpiece HP35 it held Q = 1.000 over one million sampling steps.

[GitHub](https://github.com/aai-research-lab/CalphaEBM)

---

Work here is supported by the CSUDH Startup Fund, the EFA Faculty Legacy Fund, and NIH award S10GM164901.
