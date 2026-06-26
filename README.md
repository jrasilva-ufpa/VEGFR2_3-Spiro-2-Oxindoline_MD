# Reproducible Molecular Dynamics and MM/GBSA Analysis of VEGFR-2 Complexes with Novel 3-Spiro-2-Oxindoline Derivatives

## Overview

This repository contains the computational workflow and processed data supporting the molecular dynamics (MD), MM/GBSA binding free-energy, and per-residue energy decomposition analyses reported in:

> **Ligand-Based Design and Synthesis of Novel 3-Spiro-2-Oxindoline Derivatives as Potent VEGFR-2 Inhibitors with Antiproliferative Activity and Cell Cycle Arrest**

The repository provides the files required to inspect and reproduce the computational analyses of VEGFR-2 in complex with the crystallographic reference inhibitor sorafenib and the selected synthesized compounds **4**, **5**, and **6g**.

## Scope

The computational analyses were designed to evaluate the dynamic stability and interaction patterns of VEGFR-2-ligand complexes and to provide a structural rationale for the biochemical VEGFR-2 inhibitory activity of the selected compounds.

The simulations do not establish intracellular target engagement or directly predict antiproliferative potency. Cellular activity may additionally depend on permeability, intracellular exposure, solubility, metabolism, efflux, protein binding, off-target effects, and cell-specific signaling.

## Simulated Systems

| System        | Ligand      |              Starting Structure | Independent Replicas | Aggregate Simulation Time |
| ------------- | ----------- | ------------------------------: | -------------------: | ------------------------: |
| `BAX`         | Sorafenib   | Crystal structure from PDB 4ASD |           3 × 250 ns |                    750 ns |
| `compound_4`  | Compound 4  |            Docking-derived pose |           3 × 250 ns |                    750 ns |
| `compound_5`  | Compound 5  |            Docking-derived pose |           3 × 250 ns |                    750 ns |
| `compound_6g` | Compound 6g |            Docking-derived pose |           3 × 250 ns |                    750 ns |

## Molecular Dynamics Protocol

* **Software:** AMBER22 and AmberTools
* **Protein force field:** ff14SB
* **Ligand force field:** General AMBER Force Field (GAFF)
* **Ligand charges:** RESP charges derived from HF/6-31G* electrostatic potentials
* **Protein protonation states:** Assigned with PROPKA 3.1 at physiological pH
* **Solvent model:** TIP3P water
* **Solvation box:** Rectangular periodic box extending at least 10 Å from the solute
* **Electrostatics:** Particle Mesh Ewald (PME)
* **Nonbonded cutoff:** 10 Å
* **Hydrogen constraints:** SHAKE
* **Production ensemble:** NPT, 310 K and 1 atm
* **Production time step:** 2 fs
* **Replicas:** Three independent 250 ns simulations per system

Each system underwent four minimization stages, gradual heating from 100 to 310 K over 200 ps under NVT conditions, and a seven-stage NPT equilibration protocol with progressive removal of positional restraints.

## Data Availability

This repository contains AMBER files and processed data. Large raw trajectories may not be stored directly in the GitHub repository because of file-size limitations. Wh

## Software

* AMBER22
* AmberTools
* Gaussian09
* PROPKA 3.1
* CPPTRAJ
* MMPBSA.py
* MOE 2020.09
* Python 3.10

## Citation

Please cite the associated manuscript when using these data or workflows:

> Sweify, I. R., Abdel El-wahab, H. A. A., Qayed, W. S., Hosny, Y., El-Sayed, W. M., Silva, J. R. A., and Aboul-Fadl, T. *Ligand-Based Design and Synthesis of Novel 3-Spiro-2-Oxindoline Derivatives as Potent VEGFR-2 Inhibitors with Antiproliferative Activity and Cell Cycle Arrest.* [Journal information to be added after publication].

Please also cite the archived repository version:

> Silva, J. R. A. et al. Reproducible Molecular Dynamics and MM/GBSA Analysis of VEGFR-2 Complexes with Novel 3-Spiro-2-Oxindoline Derivatives. Zenodo. [DOI].

## License

This repository is distributed under the [LICENSE NAME] license. Please consult the `LICENSE` file for details.

## Contact

**José Rogério A. Silva**
Laboratory of Computer Modeling of Molecular Biosystems (CompMBio)
Federal University of Pará, Belém, Pará, Brazil

For questions regarding the MD simulations, MM/GBSA analyses, or repository contents, please contact: [email address].
