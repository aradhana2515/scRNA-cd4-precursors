# scRNA-cd4-precursors
This repository provides a modular single-cell RNA-seq analysis scaffold built with Scanpy. 
It is designed to generalize across immune-focused datasets, including inflammatory disease biopsies.

## Quick summary
- End-to-end pipeline: QC → normalization → HVG selection → PCA → neighbors → UMAP → Leiden clustering → CD4 enrichment → diffusion pseudotime
- Demo dataset: PBMC (Scanpy `pbmc3k`) used to validate pipeline; same code works for `.h5ad` IBD inputs.
- Key finding (demo): CD4-like cells form a transcriptional manifold spanning naïve-like (CCR7/IL7R) to effector-like programs, indicating transitional precursor states.

## How to reproduce
1. Create environment (recommended with micromamba/conda)
```bash
conda env create -f environment.yml
conda activate sc-mini
