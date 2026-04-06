# Mutation Effect Prediction

Structure-aware mutation effect prediction for protein stability using hen egg-white lysozyme (1LYZ).

## Project goal

This project evaluates the likely stability effects of single-point mutations in a real protein structure.  
Using lysozyme (1LYZ) as a test case, the pipeline:

- loads a real PDB structure
- extracts sequence and residue-level structural features
- generates a controlled mutation panel
- scores mutations using interpretable stability rules
- ranks mutations as likely stabilizing, neutral, or destabilizing
- explains the results biologically

## Why this project

This project complements sequence design workflows such as ProteinMPNN and AlphaFold-based validation by focusing on mutation evaluation rather than de novo generation.

It is designed as a small, interpretable protein engineering project.

## Planned workflow

1. Load real structure (1LYZ)
2. Extract residue and structure features
3. Generate mutation panel
4. Score mutations using rule-based stability logic
5. Rank and interpret mutations
6. Optionally extend with FoldX ΔΔG

## Project structure

- `data/input/` → raw input files
- `data/processed/` → processed annotations
- `notebooks/` → step-by-step walkthrough
- `scripts/` → reusable analysis scripts
- `results/tables/` → output tables
- `results/figures/` → output plots

## Status

In progress.