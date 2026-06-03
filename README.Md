# Automated Molecular Docking Pipeline Using AutoDock Vina

## Overview

This repository presents a reproducible computational molecular docking workflow developed for the investigation of protein–ligand interactions associated with neurodegenerative disease targets. The workflow integrates protein preparation, ligand preparation, active-site identification, molecular docking, and binding affinity evaluation using a fully terminal-based computational environment.

The study was designed to demonstrate a scalable and reproducible structure-based drug discovery workflow utilizing AutoDock Vina, Open Babel, and Miniconda-managed scientific computing environments.

---

## Computational Environment

All molecular docking experiments were performed on macOS using a dedicated Miniconda environment. The complete workflow was executed through command-line tools without relying on graphical docking interfaces, ensuring reproducibility and automation.

### Software and Tools

| Software                    | Purpose                               |
| --------------------------- | ------------------------------------- |
| Miniconda                   | Environment and Package Management    |
| Python                      | Scientific Computing Environment      |
| AutoDock Vina v1.2.7        | Molecular Docking                     |
| Open Babel                  | Structure Conversion and Optimization |
| PyMOL                       | Molecular Visualization               |
| Discovery Studio Visualizer | Interaction Analysis                  |

### Environment Setup

```bash
conda create -n md python=3.11
conda activate md

conda install -c conda-forge openbabel
conda install -c conda-forge autodock-vina
```

---

## Protein and Ligand Preparation

Protein structures were obtained from the Protein Data Bank (PDB) and processed to generate docking-ready receptor structures. Ligands were prepared using Open Babel and subjected to three-dimensional geometry optimization before conversion into PDBQT format.

### Protein Preparation Workflow

* Retrieval of crystal structures from the Protein Data Bank
* Removal of unnecessary molecules and artifacts
* Structural cleaning and formatting
* Conversion to docking-compatible PDBQT format

### Ligand Preparation Workflow

* Ligand structure acquisition
* Geometry optimization
* Hydrogen addition
* Charge assignment
* Conversion to PDBQT format

---

## Active-Site Identification

Active-site coordinates were determined from experimentally resolved native ligands, cofactors, or HETATM records present within the crystal structures. The centroid coordinates of these molecules were calculated and subsequently used to define biologically relevant docking search spaces.

This strategy minimizes false-positive binding predictions and focuses docking calculations on experimentally validated binding pockets.

---

## Docking Methodology

A semi-flexible molecular docking protocol was employed in which receptor structures remained rigid while ligands were allowed to explore multiple conformational orientations within the active site.

AutoDock Vina's global optimization algorithm was utilized to identify energetically favorable binding poses and estimate binding affinities.

### Docking Parameters

| Parameter           | Value                                       |
| ------------------- | ------------------------------------------- |
| Docking Software    | AutoDock Vina v1.2.7                        |
| Protein Preparation | Open Babel                                  |
| Ligand Preparation  | Open Babel with 3D Optimization             |
| Docking Type        | Semi-flexible Molecular Docking             |
| Grid Generation     | Native Ligand/HETATM Centroid-Based         |
| Search Algorithm    | AutoDock Vina Global Optimization Algorithm |
| Output Modes        | Top 10 Binding Poses                        |
| Exhaustiveness      | 32                                          |
| Grid Dimensions     | 25 Å × 25 Å × 25 Å                          |

---

## Terminal-Based Docking Execution

The molecular docking workflow was executed entirely through terminal commands.

### Representative Docking Command

```bash
vina --receptor receptor.pdbqt \
     --ligand ligand.pdbqt \
     --center_x X \
     --center_y Y \
     --center_z Z \
     --size_x 25 \
     --size_y 25 \
     --size_z 25 \
     --exhaustiveness 32 \
     --num_modes 10 \
     --out output.pdbqt
```

### Parameter Description

| Parameter                    | Description                              |
| ---------------------------- | ---------------------------------------- |
| receptor                     | Prepared protein structure               |
| ligand                       | Prepared ligand structure                |
| center_x, center_y, center_z | Active-site coordinates                  |
| size_x, size_y, size_z       | Docking search space dimensions          |
| exhaustiveness               | Search depth for conformational sampling |
| num_modes                    | Number of predicted binding poses        |
| out                          | Docking output file                      |

---

## Computational Skills Demonstrated

* Molecular Docking
* Structure-Based Drug Design
* Computer-Aided Drug Design (CADD)
* Protein Structure Preparation
* Ligand Preparation and Optimization
* Active-Site Identification
* Virtual Screening
* Protein–Ligand Interaction Analysis
* Bioinformatics
* Molecular Modeling
* Scientific Computing
* Terminal-Based Workflow Automation
* Reproducible Research Computing
* Miniconda Environment Management

---

## Repository Structure

```text
proteins/
│
├── ACHE
├── COMT
├── DRD2
├── MAOB
└── SLC6A3

ligands/
│
├── Apigenin
├── Kaempferol
├── Luteolin
├── Quercetin
├── Gallic Acid
├── Vanillic Acid
├── Linoleic Acid
└── Sterol

scripts/
configs/
docking_results/
images/
```

---

## Reproducibility and Scientific Rigor

The entire workflow was designed with reproducibility as a primary objective. All docking calculations were executed through a standardized command-line pipeline within a controlled Miniconda environment. This approach ensures transparency, reproducibility, scalability, and suitability for future virtual screening and structure-based drug discovery applications.

---

## Research Applications

* Neurodegenerative Disease Research
* Drug Discovery
* Structure-Based Drug Design
* Virtual Screening
* Computational Biology
* Bioinformatics
* Pharmacoinformatics
* Molecular Modeling

---

## Author

**Rituraj Kumar**

**Research Interests**

Computational Biology • Molecular Docking • Molecular Dynamics Simulation • Drug Discovery • Bioinformatics • Pharmacology • Computer-Aided Drug Design (CADD)

---

## License

This project is released under the MIT License.
