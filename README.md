# Blind-Wine-Tasting
Peptide-based colorimetric sensor array for red wine discrimination using UV-visible spectroscopy and machine learning. MSc dissertation.

## Overview
A 14-sensor peptide array, using three indicator-metal chemistries (Cu²⁺–PCV, Cu²⁺–CAS, Ni²⁺–BPR), was applied to 12 red wines across a 384-well plate design with 6 replicates per wine. Absorbance was recorded from 350-800 nm at 2 nm intervals. The analysis covers wavelength selection by ANOVA F-statistic, dimensionality reduction (PCA, UMAP), classification by LDA under nested leave-one-out cross-validation, and hierarchical clustering.

## Repository Structure
data/raw -> Plate reader exports (.xlsx)
data/processed/ -> Tidied datasets produced by the import notebooks
notebooks/ -> Analysis Notebooks

## Running order
The notebooks share files on disk and must be run in order:
1. 01_384well_Import.ipynb — imports raw plate files, writes master_df_384.csv
2. 02_384well_EDA.ipynb — exploratory analysis
3. 03_384well_Analysis.ipynb — wavelength selection, PCA/UMAP, LDA, nested LOOCV; writes compact_matrix_384.csv
4. 04_384well_Clustering.ipynb — hierarchical clustering, silhouette and ARI

Paths are relative, so the folder structure should be kept intact.

## 96-well Pilot
The 96-well pilot notebooks cover data import and exploratory analysis only. This work was superseded by the 384-well design, and no classification or clustering was performed on the pilot data. It is included for reference and does not contribute to the reported results.

## Requirements
Python 3.13 with pandas, numpy, scipy, scikit-learn, umap-learn, seaborn, matplotlib.
