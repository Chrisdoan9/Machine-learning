# Predicting Cell Types from scRNA-seq Using random forest

## Motivation
Cell type annotation is a core task in single-cell analysis. Here, I explore
how classical machine learning models can predict cell types from gene
expression data and identify biologically meaningful marker genes.

## Dataset
- PBMC scRNA-seq dataset
- 2,700 cells, annotated cell types

## Methods
- Preprocessing: log-normalization, HVG selection
- Models: Random Forest
- Evaluation: accuracy, F1-score, confusion matrix
