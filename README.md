# Single-Cell RNA Sequencing Analysis Pipeline

This repository provides a workflow for analyzing single-cell RNA sequencing (scRNA-seq) data using Seurat. It includes steps for quality control, normalization, clustering, dimensionality reduction, batch effect correction with Harmony, visualization techniques, and downstream analysis for biological insights.

The dataset us avialable at : https://cellxgene.cziscience.com/e/9813a1d4-d107-459e-9b2e-7687be935f69.cxg/

**Workflow Overview**


**1.) Data Loading**
  Load the scRNA-seq data in RDS format for downstream processing.
  Ensure the dataset contains relevant metadata for effective analysis.

**2.) Quality Control**
  Calculate mitochondrial gene percentages to assess cell health.
  Filter out low-quality cells based on RNA and feature counts thresholds.
  Objective: Retain high-quality, biologically relevant data.

**3.) Data Normalization and Scaling**
  Normalize RNA expression with LogNormalize.
  Identify highly variable genes for dimensionality reduction.
  Scale data to mitigate confounding effects of unwanted sources of variation.

**4.) Dimensionality Reduction**
  Perform PCA to identify principal components that explain most variance.
  Use the elbow plot to select significant PCs for clustering and visualization.

**5.) Clustering**
  Build a nearest-neighbor graph and cluster cells based on PCA embeddings.
  Visualize clusters using UMAP to identify distinct cell populations.

**6.) Batch Effect Correction**
  Correct for batch effects using Harmony, grouping by metadata (e.g., patient or disease).
  Recompute clusters and embeddings after batch correction for unbiased results.

**7.) Visualization**
  Generate UMAP plots to visualize:
  Clusters (Seurat-generated).
  Samples (grouped by patient).
  Disease conditions (grouped by disease).
  Compare before and after batch correction using multiple layout approaches.
