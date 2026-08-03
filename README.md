# AAI Research Lab

### Laboratory for Computational Science

Department of Physics · California State University, Dominguez Hills
Labs C131 and C121, Natural Science Building · 1000 E Victoria Street, Carson, CA 90747

🌐 [aai-research-lab.github.io](https://aai-research-lab.github.io) · 💼 [LinkedIn](https://www.linkedin.com/company/aai-research-labs) · ✉️ aaina [at] csudh.edu

---

## Welcome

We are advancing research at the intersection of physics, chemistry, and biology, harnessing the power of mathematical and computational tools to address challenging questions in biophysics and protein design for applications in biomedicine and biotechnology. [Join us](#join-us) in this exciting frontier of computational science and be a part of revolutionizing the future of healthcare.

We believe in the transformative power of computational science to revolutionize the way we study biological systems such as proteins. Our research doesn't just stay in the lab — it has the potential to create real-world solutions like the development of new therapeutic proteins that can have positive impact on people's lives.

## Research

**Biophysics.** We study the principles of physics that govern biomolecular interactions and use and develop computational and machine learning methods to understand the dynamics of proteins.

**Protein Design.** We utilize AI and biophysical understanding to design and engineer novel proteins with entirely new structural and functional properties.

**Drug Discovery.** We apply protein design techniques to immunogen and antibody design to tackle practical problems in drug discovery for neurodegenerative diseases.

## Software

### FastMDXplora

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

- Explore a protein's full dynamics with one command, covering setup, simulation, analysis, and reporting
- Build a protein–ligand system from a PDB identifier alone: the ligand is identified, its chemistry retrieved, and its protonation settled in the binding site — with a refusal rather than a guess where the structure is ambiguous
- Probe protein–ligand binding automatically, with analyses for pose stability, contacts, and hydrogen bonds
- Reach beyond plain MD with built-in PLUMED enhanced sampling: metadynamics, umbrella sampling, steered MD
- Design, start, watch, and review an exploration from a browser, with a 3D viewer and live telemetry
- Scale from a quick single-protein exploration to large parallel campaigns, driven the same way from the CLI or the Python API

```bash
pip install fastmdxplora
```

Analysis and reporting are pure pip. Setup and simulation additionally require OpenMM and PDBFixer from conda-forge — see the [installation guide](https://fastmdxplora.readthedocs.io/en/latest/installation.html).

[GitHub](https://github.com/aai-research-lab/FastMDXplora) · [Documentation](https://fastmdxplora.readthedocs.io) · [PyPI](https://pypi.org/project/fastmdxplora/) · MIT licence

The foundational methodology is described in the FastMDAnalysis paper below. A further publication describing FastMDXplora is in preparation.

## Publications

### 2026

**FastMDAnalysis: Software for Automated Analysis of Molecular Dynamics Trajectories**
A. Aina, D. Kwan
_Journal of Computational Chemistry_ **47**(8), e70350 (2026)
[doi:10.1002/jcc.70350](https://doi.org/10.1002/jcc.70350) · [code](https://github.com/aai-research-lab/FastMDAnalysis)

### 2024

**Cyclization Scaffolding for Improved Vaccine Immunogen Stability: Application to Tau Protein in Alzheimer's Disease**
S. C. C. Hsueh, M. Nijland, A. Aina, S. S. Plotkin
_Journal of Chemical Information and Modeling_ **64**(6), 2035–2044 (2024)
[doi:10.1021/acs.jcim.3c01556](https://doi.org/10.1021/acs.jcim.3c01556)

### 2023

**De Novo Design of a β-Helix Tau Protein Scaffold: An Oligomer-Selective Vaccine Immunogen Candidate for Alzheimer's Disease**
A. Aina, S. C. C. Hsueh, E. Gibbs, X. Peng, N. R. Cashman, S. S. Plotkin
_ACS Chemical Neuroscience_ **14**(15), 2603–2617 (2023)
[doi:10.1021/acschemneuro.3c00007](https://doi.org/10.1021/acschemneuro.3c00007) · [PDF](assets/pdf/Aina2023DeNovoDesign.pdf)

**PROTHON: A Local Order Parameter-Based Method for Efficient Comparison of Protein Ensembles**
A. Aina, S. C. C. Hsueh, S. S. Plotkin
_Journal of Chemical Information and Modeling_ **63**(11), 3453–3461 (2023)
[doi:10.1021/acs.jcim.3c00145](https://doi.org/10.1021/acs.jcim.3c00145) · [PDF](assets/pdf/Aina2023Prothon.pdf) · [code](https://github.com/aai-research-lab/Prothon)

### 2022

**Optimizing Epitope Conformational Ensembles Using α-Synuclein Cyclic Peptide "Glycindel" Scaffolds: A Customized Immunogen Method for Generating Oligomer-Selective Antibodies for Parkinson's Disease**
S. C. C. Hsueh, A. Aina, A. Yu. Roman, N. R. Cashman, X. Peng, S. S. Plotkin
_ACS Chemical Neuroscience_ **13**(15), 2261–2280 (2022)
[doi:10.1021/acschemneuro.1c00567](https://doi.org/10.1021/acschemneuro.1c00567)

**Ensemble Generation for Linear and Cyclic Peptides Using a Reservoir Replica Exchange Molecular Dynamics Implementation in GROMACS**
S. C. C. Hsueh, A. Aina, S. S. Plotkin
_The Journal of Physical Chemistry B_ **126**(49), 10384–10399 (2022)
[doi:10.1021/acs.jpcb.2c05470](https://doi.org/10.1021/acs.jpcb.2c05470)

**Rational Generation of Monoclonal Antibodies Selective for Pathogenic Forms of Alpha-Synuclein**
E. Gibbs, B. Zhao, A. Roman, S. S. Plotkin, X. Peng, S. C. C. Hsueh, A. Aina, J. Wang, C. Shyu, C. K. Yip, S.-E. Nam, J. M. Kaplan, N. R. Cashman
_Biomedicines_ **10**(9), 2168 (2022)
[doi:10.3390/biomedicines10092168](https://doi.org/10.3390/biomedicines10092168)

### 2021

**Structural fluctuations and mechanical stabilities of the metamorphic protein RfaH**
B. Seifi, A. Aina, S. Wallin
_Proteins: Structure, Function, and Bioinformatics_ **89**(3), 289–300 (2021)
[doi:10.1002/prot.26014](https://doi.org/10.1002/prot.26014)

### 2017

**Multisequence algorithm for coarse-grained biomolecular simulations: Exploring the sequence-structure relationship of proteins**
A. Aina, S. Wallin
_The Journal of Chemical Physics_ **147**(9) (2017)
[doi:10.1063/1.4986933](https://doi.org/10.1063/1.4986933) · [PDF](assets/pdf/Aina2017Multisequence.pdf)

## Teaching

Courses taught by Dr. Aina at California State University, Dominguez Hills.

| Course  | Title                     | Terms                                         |
| ------- | ------------------------- | --------------------------------------------- |
| BPH 330 | Biological Physics        | Fall 2024, Fall 2025                          |
| BPH 406 | Computational Biophysics  | Spring 2025                                   |
| PHY 120 | Elements of Physics I     | Fall 2024, Summer 2025                        |
| PHY 122 | Elements of Physics II    | Spring 2025, Spring 2026 (+ Lab), Summer 2026 |
| PHY 346 | Thermal Physics           | Fall 2025                                     |
| PHY 350 | Electromagnetic Theory I  | Fall 2025                                     |
| PHY 352 | Electromagnetic Theory II | Spring 2026                                   |

## Team

### Adekunle Aina, Ph.D. — Lead Scientist

✉️ aaina [at] csudh.edu · 🌐 [LinkedIn](https://www.linkedin.com/in/ainaadekunle) · [ORCID](https://orcid.org/0000-0002-8215-7452) · [Google Scholar](https://scholar.google.com/citations?user=t7ARddEAAAAJ)

Dr. Aina is an Assistant Professor of Physics and Biophysics at California State University, Dominguez Hills. He received his Ph.D. in Physics at the University of British Columbia. His research focuses on computational protein design of immunogens for neurodegenerative diseases. Previously, he was a College Professor at Okanagan College and worked as an Associate Scientist at the biotech company ProMIS Neurosciences. He is interested in computational science to tackle problems at the intersection of physics, chemistry, and biology for applications in biomedicine and biotechnology.

### Derrick Kwan — Research Assistant

✉️ dkwan4 [at] toromail.csudh.edu · 🌐 [LinkedIn](https://www.linkedin.com/in/derrick-kwan-5644b52b9)

Derrick is a student at the California Academy of Math and Science and a Research Assistant at AAI Research Lab. He is interested in applying computational methods to address challenges in biotechnology.

### Alumni

#### Santiago T. Garcia — Research Intern

✉️ sgarcia1 [at] toromail.csudh.edu · 🌐 [LinkedIn](https://www.linkedin.com/in/santiago-tecuanhuey-garcia)

Santi is a Computer Science student at California State University, Dominguez Hills. He was a GPS Research Intern at AAI Research Lab. He is interested in computational biology.

#### Jessica Barrios — Research Intern

✉️ jbarrios62 [at] toromail.csudh.edu · 🌐 [LinkedIn](https://www.linkedin.com/in/jessica-lynn-barrios-b8184a297)

Jessica is a Computer Science student at California State University, Dominguez Hills. She was a GPS Research Intern at AAI Research Lab, as well as a Lead Technician at Toyota's CISE Fabrication Lab. She is interested in computational biology, data analysis, and software development.

#### Jessie Flores — Research Intern

✉️ jflores534 [at] toromail.csudh.edu · 🌐 [LinkedIn](https://www.linkedin.com/in/jessie-flores)

Jessie is a Computer Science student at California State University, Dominguez Hills. He was an Intern at AAI Research Lab. He is interested in computational biology, data analysis, and software development.

#### Daira Aguilar — Research Intern

✉️ daguilar115 [at] toromail.csudh.edu · 🌐 [LinkedIn](https://www.linkedin.com/in/daira-aguilar-552434307)

Daira is a Computer Science student at California State University, Dominguez Hills. She was a GPS Research Intern at AAI Research Lab. She is interested in computational science and machine learning.

#### Aaron Demesa — Research Intern

✉️ ademesa1 [at] toromail.csudh.edu

Aaron is a Biology student at California State University, Dominguez Hills. He was a GPS Research Intern at AAI Research Lab. He is interested in computational biology.

#### Alyssa Shaw — Research Intern

✉️ ashaw36 [at] toromail.csudh.edu

Alyssa is a Computer Technology student at California State University, Dominguez Hills. She was a GPS Research Intern at AAI Research Lab. She is interested in computational science.

#### Guadalupe Alonso-Aguilar — Research Intern

✉️ galonsoaguilar1 [at] toromail.csudh.edu

Guadalupe is a student in the Department of Chemistry and Biochemistry at California State University, Dominguez Hills. She was a GPS Research Intern at AAI Research Lab. She is interested in computational biology.

#### Oliche Brown — Research Intern

✉️ obrown6 [at] toromail.csudh.edu · 🌐 [LinkedIn](https://www.linkedin.com/in/oliche-brown-a14a27338)

Oliche is a Biology student at California State University, Dominguez Hills. She was a GPS Research Intern at AAI Research Lab. She is interested in computational biology.

## News

**1 Jul 2026** — The lab is part of a **\$30,000** CSU LIFT Grant for _Future-Forward Biophysics: A Program-Level Durable Skills Pathway through VR-, AI-, Research-, and Experiential Learning_. PI: Horace Crogman; Dr. Aina is a Co-PI.

**29 Mar 2026** — Our manuscript on **FastMDAnalysis** is published in the _Journal of Computational Chemistry_. One command gives a full molecular dynamics analysis plus presentation slides, with over 90% less code than standard workflows. [Paper](https://doi.org/10.1002/jcc.70350) (open access) · [Software](https://github.com/aai-research-lab/FastMDAnalysis)

**1 Mar 2026** — Dr. Aina gave an oral presentation titled _"Automated Analysis of Molecular Dynamics Trajectories"_ at the CSUDH Research Symposium.

**1 Feb 2026** — Dr. Aina presented a poster on _Efficient Comparison of Protein Conformational Ensembles_ at the 70th Annual Meeting of the Biophysical Society in San Francisco.

**1 Nov 2025** — Dr. Aina gave an oral presentation titled _"Automated Analysis of Molecular Dynamics Trajectories with FastMDAnalysis"_ at the 5th Annual 3×2 Research Presentations, CSU Dominguez Hills.

**1 Oct 2025** — Dr. Aina attended the Cal-Bridge Fall Conference at UC Irvine.

**29 Sep 2025** — Congratulations to Oliche who has been awarded the Fall 2025 Undergraduate Research Award!

**25 Sep 2025** — Dr. Aina participated in The 4th Annual Meet a Mentor Event at CSU Dominguez Hills, showcasing research opportunities in computational science at AAI Research Lab.

**12 Sep 2025** — Four new research students: Jessie Flores, Daira Aguilar, Santiago Garcia, and Jessica Barrios join AAI Research Lab. Welcome to you all!

**1 Jul 2025** — Dr. Aina gave an invited talk titled _"Protein Immunogen Engineering with AI Algorithms"_ at the MSEIP Summer Program, CSU Dominguez Hills.

**1 Jun 2025** — Dr. Aina received a **\$6,000** EFA Faculty Legacy Fund award for _Deep Learning the Energy Landscape of a Coarse-Grained Model of Proteins_.

**1 Apr 2025** — The lab is part of a **\$200,000** California Learning Lab award for _Revolutionizing STEM Education: Integrating AI and Virtual Reality to Enhance Learning and Engagement_. PI: Horace Crogman; Dr. Aina is a Co-PI.

**1 Mar 2025** — Dr. Aina gave an oral presentation titled _"Design of Multi-Epitope Protein Immunogens with AI Algorithms"_ at the CSUDH Research Symposium.

**15 Jan 2025** — Dr. Aina attended the inaugural BioLogic Summit, _Demystifying AI/ML for Biologic Drug Development_, in San Diego, California.

**4 Dec 2024** — Dr. Aina gave an invited seminar talk titled _"Computational Protein Design of Immunogens for Neurodegenerative Diseases"_ at the Department of Chemistry and Biochemistry, CSU Long Beach.

**3 Dec 2024** — Dr. Aina gave a speech about AAI Research Lab at the inaugural College of Natural and Behavioral Sciences Open House.

**21 Nov 2024** — The 3rd Annual Meet a Mentor Event at CSU Dominguez Hills. Dr. Aina participated by showcasing research opportunities in computational science at AAI Research Lab.

**14 Nov 2024** — Dr. Aina presented at The 4th Annual CSUDH 3x2 Research Presentations.

**5 Nov 2024** — Three (3) Guided Pathways for STEM (GPS) students: Oliche Brown, Alyssa Shaw, and Guadalupe Alonso-Aguilar join AAI Research Lab.

**27 Aug 2024** — Dr. Aina was invited to present at the Department of Chemistry and Biochemistry, California State University Long Beach.

**20 Aug 2024** — AAI Research Lab is established with a **\$70,000** CSUDH Startup Fund award to Dr. Aina, for the project _Establishing a Computational Biophysics Research Laboratory_.

**19 Aug 2024** — AAI Research Lab opens at California State University Dominguez Hills.

**15 Aug 2024** — Physics chair Dr. John Price welcomes Dr. Aina to CSUDH.

<details>
<summary>Read the full welcome letter</summary>

**Welcome to Dr. Aina, new Physics faculty member!**

Hi all:

Please join me in welcoming Dr. Adekunle Aina to the CSUDH Physics Department! Dr. Aina comes to us from Okanagan College in Kelowna, Canada, where he served as an instructor in Mathematics and Statistics. He is joining Dr. Crogman in our newly-formed Biophysics major, which I am sure will soon take the University by storm.

Dr. Aina received his Associate of Science degree in Mathematics, Physics, and Chemistry from Ahmadu Bello University in Zaria, Nigeria, and his Bachelor of Science degree in Applied/Engineering Physics from the University of Lagos in Lagos, Nigeria. He then moved to Canada, receiving his Master of Science degree in Physics from the University of Newfoundland in Newfoundland, Canada, and his Ph.D. In Physics and Biophysics from the University of British Columbia in Vancouver, Canada. He received his Ph.D. in 2023.

Side note: UBC is also the home of TRIUMF, a particle accelerator where I performed my first published physics experiment as an undergraduate way back in 1985. Yes, I'm old. Back to Dr. Aina...

Dr. Aina did his doctoral dissertation on "Computational Modeling and Design of Oligomer Selective Immunogens for Parkinson's and Alzheimer's Disease". It's available online, but I'll let you search for it yourself – it's not that hard to find.

Dr. Aina has performed research in Computational Physics and Biophysics, Bioinformatics, and Data Science. He brings with him a wealth of knowledge and experience in the field, and I am confident that he will be a tremendous addition to the Physics Department.

As we begin the new semester, please take a moment to stop by his office and say hi, and welcome into our community.

> **Dr. John Price**  
> Professor and Chair, Department of Physics  
> California State University Dominguez Hills

</details>

**14 Aug 2024** — Dr. Aina arrives at California State University Dominguez Hills.

## Join us

We are a multidisciplinary team harnessing advanced mathematical and computational tools to address challenging questions in biophysics, protein design, and drug discovery.

We seek curious, motivated students and researchers with a strong foundation in mathematics, physics, chemistry, biology or computer science. If you are interested in biological problems and deepening your research expertise in an interdisciplinary field, we want you on our team. Join us in a collaborative environment to advance research for applications in biomedicine and biotechnology. Our work goes beyond the lab, aiming to design innovative therapeutic proteins that can have profound impact on people's health.

Please contact [Dr. Aina](https://www.linkedin.com/in/ainaadekunle) if you are interested in joining our research efforts or collaborating with us. We are always eager to connect with bright minds, whether you're a student, a researcher, or an industry professional.

---

_This repository is also the source for the lab website. For build, editing and deployment instructions, see [CONTRIBUTING.md](CONTRIBUTING.md)._
