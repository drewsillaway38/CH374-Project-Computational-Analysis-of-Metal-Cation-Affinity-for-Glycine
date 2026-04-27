# CH374-Project-Computational-Analysis-of-Metal-Cation-Affinity-for-Glycine
Repository to store data from my CH374 research project. This study used high-level computational chemistry to investigate the thermodynamic and structural properties of metal-cation binding to glycine, the simplest amino acid. Binding affinity and the structural stability of both non-zwitterionic and zwitterionic glycine isomers were quantified. 

# Computational Analysis of Metal Cation Affinity for Glycine
**Author:** Drew Sillaway  
**Date:** April 27, 2026  
**Course:** CH 374 - Physical Chemistry II

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Methodology](#methodology)
3. [Key Findings](#key-findings)
4. [File Structure](#file-structure)
5. [Navigation & Usage](#navigation--usage)
6. [Prerequisites](#prerequisites)

---

## Project Overview
This study utilizes high-level computational chemistry to investigate the thermodynamic and structural properties of metal-cation binding to **glycine**, the simplest amino acid. The research quantifies the factors influencing binding affinity and the structural stability of both non-zwitterionic and zwitterionic glycine isomers in the presence of various biologically and chemically relevant metal ions.

### Methodology
All electronic structure calculations were performed using the **ORCA software package**. 
* **Theory:** Density Functional Theory (DFT) with the **B3LYP** functional.
* **Corrections:** Grimme’s **D3 correction** with Becke-Johnson (BJ) damping for long-range dispersion.
* **Basis Set:** **cc-pVTZ** to ensure high convergence for both organic ligands and metal centers.
* **Solvation:** Comparison between **Implicit Water Solvation** (C-PCM bulk-solvent effects) and **Explicit Water Solvation** (5 coordinated water molecules) to evaluate micro-solvation impact.

---

## Key Findings
* **Charge Density & Oxidation State:** A direct correlation was observed between ionic radius and binding affinity; smaller cations and divalent ($2+$) ions showed significantly higher binding energies than monovalent ($1+$) cations.
* **Isomeric Stability:** Metal coordination is a critical factor in stabilizing the zwitterionic state; results showed stronger binding to zwitterions than non-zwitterions.
* **Solvation Impact:** Explicit water models yielded greater binding affinity than implicit models, suggesting that local hydration plays a non-negligible role in enhancing complex stability.
* **Structural Metrics:** Higher binding energies correlated directly with contracted nitrogen–metal (non-zwitterions) and metal-to-proximal-carbon (zwitterions) distances.

---

## File Structure
The repository is organized by molecular state, solvation model, and file type.

| Component | Naming Convention |
| :--- | :--- |
| **Metals** | Identified by element followed by charge (e.g., `Li1`, `Mg2`) |
| **Glycine** | Labeled as `zwitter` or `nonzwitter` |
| **Implicit Solvation** | File names end in `water` |
| **Explicit Solvation** | File names begin with `explicit` |

### Directory Breakdown
* **`DATA ANALYSIS.ipynb`**: Jupyter Notebook containing all Python code for result analysis and data visualization.
* **`.trj/`**: Contains `.trj` files generated during structure optimizations.
* **`.xyz structures/`**: Contains `.xyz` coordinates for glycine complexes, metal cations, and isolated glycine forms.
* **`all_logs-nonzwitter/`**: ORCA log files for non-zwitterionic glycine-metal complexes.
* **`all_logs-zwitter/`**: ORCA log files for zwitterionic glycine-metal complexes.
* **`glycine-nonzwitter/`**: Log files for isolated non-zwitterionic glycine molecules.
* **`glycine-zwitter/`**: Log files for isolated zwitterionic glycine molecules.
* **`metals/`**: Log files for isolated metal cations.

---

## Navigation & Usage
1. **Initial Review:** Start with the isolated component logs in `metals/` and `glycine-zwitter/` or `glycine-nonzwitter/` to understand the baseline energies.
2. **Complex Analysis:** Navigate to the `all_logs` folders to review the binding interactions of the specific metal-glycine complexes.
3. **Visualization:** Use the `.xyz structures/` folder with a molecular viewer (e.g., Avogadro or VMD) to inspect bond lengths and coordination geometry.
4. **Data Processing:** Run the `DATA ANALYSIS.ipynb` notebook to see the Python implementation of the binding energy calculations and generated plots.

---

## Prerequisites
To interact with these files, the following are recommended:
* **Computational Chemistry:** ORCA (for running/reading log files)
* **Visualization:** Avogadro, VMD, or ChemCraft
* **Analysis:** Python 3.x with the following libraries:
  * `Jupyter`
  * `Matplotlib` (for plotting binding energy data)
  * `Pandas/Numpy`
