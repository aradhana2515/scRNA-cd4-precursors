# scRNA-cd4-precursors

A reproducible single-cell RNA-seq analysis pipeline (Scanpy) for identifying CD4⁺ transitional activation states and precursor manifolds.

This repository demonstrates an end-to-end workflow for immune-focused datasets and is structured to be directly transferable to inflammatory disease contexts (e.g., IBD biopsies).

---

## Scientific Motivation

Immune pathology often emerges from transitional cellular states rather than fully differentiated effector populations. Resolving these intermediate activation programs is critical for identifying early regulatory checkpoints and therapeutically actionable precursors.

This project demonstrates how single-cell RNA-seq analysis can be used to uncover such state continua within CD4⁺ T cell compartments.

---

## Pipeline Overview

The workflow includes:

- Quality control filtering (low-gene, high-mitochondrial cells removed)
- Library-size normalization and log transformation
- Highly variable gene (HVG) selection
- PCA dimensionality reduction
- k-nearest neighbor graph construction
- UMAP visualization
- Leiden clustering
- Marker-based CD4⁺ enrichment
- Diffusion pseudotime trajectory inference

All analysis is implemented using Scanpy in Python.

---

## Demo Dataset

The Scanpy `pbmc3k` dataset is used to validate the pipeline.

Key result (demo):

Within the CD4-enriched subset, diffusion pseudotime reveals a transcriptionally continuous manifold spanning:

- Naïve-like programs (CCR7⁺ / IL7R⁺)
- Transitional activation states
- Effector-associated signatures (e.g., GZMB⁺ where present)

This continuum is consistent with the presence of precursor states that may seed inflammatory effector populations in disease contexts.

---

## Translational Relevance

The pipeline is structured to be directly applied to inflammatory disease datasets (e.g., IBD biopsies), where enrichment of transitional CD4⁺ states may reveal:

- Early activation programs
- Pathogenic differentiation trajectories
- Molecular drivers of patient heterogeneity
- Potential therapeutic intervention points

---

## Repository Structure
```text
scRNA-cd4-precursors/
├── notebooks/
│   └── cd4_activation_analysis.ipynb
├── environment.yml
├── README.md
├── LICENSE
└── .gitignore
```

## How to Reproduce

### 1. Create environment

```bash
conda env create -f environment.yml
conda activate sc-mini
```

### 2. Launch notebook
```bash
jupyter notebook notebooks/cd4_activation_analysis.ipynb
```

### 3. Apply to your own dataset
To analyze a disease dataset:
- Place an `.h5ad` file in a data/ directory
- Modify the data-loading cell in the notebook accordingly
- Re-run the pipeline
The analysis is designed to generalize across immune-focused single-cell datasets.

---
## Author
**Aradhana**

PhD Student, Biomedical Engineering
