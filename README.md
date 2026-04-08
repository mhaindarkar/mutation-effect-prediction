# Protein Mutation Stability Pipeline

Structure-aware prediction of mutation effects on protein stability using hen egg-white lysozyme (PDB: 1LYZ).

This project combines residue-level structural analysis, biologically interpretable rule-based scoring, and FoldX energy evaluation to assess whether selected single-point mutations are likely to be tolerated or destabilizing.

---

## Summary

This project focuses on mutation evaluation, complementing protein design workflows (e.g., ProteinMPNN).

It answers a key question in protein engineering:

**If we introduce a mutation, will it stabilize or destabilize the protein?**

Using a real protein structure (1LYZ), the pipeline:

* loads and parses a real PDB structure
* extracts residue-level structural features
* classifies residues by environment (core, intermediate, surface)
* generates a controlled mutation panel
* predicts mutation effects using interpretable rules
* validates predictions using FoldX energy calculations

---

## Project Goal

Build a small, realistic, and interpretable mutation-analysis pipeline that:

* uses real structural biology data
* applies biologically meaningful mutation strategies
* produces interpretable stability predictions
* validates results using physics-based tools (FoldX)

---

## Workflow

1. Load real protein structure (1LYZ)
2. Extract amino acid sequence and residue table
3. Compute structural features using DSSP

   * secondary structure
   * solvent accessibility (RSA)
   * residue environment (core / intermediate / surface)
4. Select mutation sites

   * 3 buried hydrophobic core residues
   * 3 exposed polar/charged surface residues
5. Generate mutation panel

   * conservative
   * moderate
   * disruptive
6. Apply rule-based stability scoring
7. Run FoldX mutation modeling
8. Compare rule-based predictions with FoldX results
9. Interpret results using protein biophysics principles

---

## 🧪 Selected Mutation Sites

Core residues (buried)

* L8
* V29
* L56

Surface residues (exposed)

* D18
* R73
* Q41

---

## 📊 Key Results

* Total mutations analyzed: 18
* Stabilizing (rule-based): 6
* Destabilizing (rule-based): 12

Strongest stabilizing/tolerated mutations:

* L8I
* V29I
* L56I
* Q41N
* R73K

Strongest destabilizing mutations:

* L8D
* V29D
* L56D
* R73F
* Q41F

---

## Biological Insights

* Core residues are highly sensitive to mutation
* Introducing charged residues into the hydrophobic core is strongly destabilizing
* Conservative hydrophobic substitutions in the core are often tolerated
* Surface residues are more mutation-tolerant than core residues
* Mutation chemistry matters:

  * hydrophobic → charged (core) = highly unfavorable
  * polar/charged → hydrophobic (surface) = unfavorable but less severe

---

## FoldX Validation

The mutation panel was evaluated using FoldX after structure repair (RepairPDB).

This adds a second layer:

* Rule-based model → interpretable biochemical reasoning
* FoldX → structure-based energy evaluation

---

## Visualizations

Mutation effect distribution
![Mutation Effect Distribution](results/figures/mutation_effect_distribution.png)

Rule-based vs FoldX comparison
![Rule vs FoldX](results/figures/rule_vs_foldx.png)

---

## Tech Stack

* Python
* Biopython
* Pandas
* Jupyter Notebook
* DSSP
* FoldX

---

## Project Structure

data/
input/
processed/

foldx/
input/
output/

notebooks/
01_load_structure.ipynb
02_residue_features.ipynb
03_generate_mutations.ipynb
04_score_mutations.ipynb
05_interpret_results.ipynb
06_foldx_ddg_analysis.ipynb

results/
tables/
figures/

scripts/
tools/

---

## How to Run

conda env create -f environment.yml
conda activate mutation-effect-prediction
jupyter lab

FoldX setup:
Place FoldX executable in:
tools/FoldX

---

## What This Project Demonstrates

* structure-aware mutation analysis
* integration of biology and computation
* interpretable protein stability reasoning
* use of real protein engineering tools

---

## Future Work

* refine FoldX vs rule-based agreement
* extend to multiple proteins
* integrate ML models

---

## 👤 Author

Vaibhav Mhaindarkar
Protein Biochemistry → Bioinformatics → Protein Engineering
