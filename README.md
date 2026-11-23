# Multivariate and Spatial Analysis in R

Academic workshop exploring principal component analysis (PCA) and spatial clustering, using music features and Colombian municipal geography.

## Analyses

### 1. Principal component analysis of Spotify tracks
- Standardizes numerical features and calculates the covariance matrix and eigendecomposition manually.
- Compares manual PCA results with `prcomp()`.
- Visualizes principal components by playlist genre using `factoextra`.
- Dataset: `data/spotify.csv`.

### 2. Spatial clustering of Colombian municipalities
- Retrieves second-level Colombian administrative boundaries using `geodata::gadm()`.
- Calculates municipal centroids and implements a four-cluster iterative k-means procedure.
- Compares the manual implementation with R's `kmeans()`.
- Administrative boundaries are downloaded by `geodata` when the analysis runs; they are not bundled here.

## Repository structure

```text
analysis/workshop-04-pca-spatial-clustering.Rmd
 data/spotify.csv
 README.md
```

## Requirements

R packages: `dplyr`, `factoextra`, `geodata`, `sf`, `ggplot2`, plus the R Markdown/PDF toolchain for PDF output.

## Reproducibility notes

This repository preserves the original coursework analysis and interpretations. **It has not been fully executed or verified.** Before knitting, change the Spotify data import in the R Markdown to `read.csv("../data/spotify.csv")` if knitting from the `analysis/` directory. The geographic data download requires internet access and a writable path.

**Known issue:** Exercise 6 references `accidentes$Severity`, but `accidentes` is not defined in this document and no accident dataset is supplied. Its accident-severity PCA plot does not match the surrounding municipal clustering discussion. That block must be reviewed or replaced with an appropriate spatial cluster map before the document can be considered reproducible. No replacement figure or result has been invented here.

## Attribution

Code and analysis: Juanita Guerrero (as reported by the author). The original academic submission lists a course partner; the source document is retained unchanged.

## Context

Prepared as a quantitative biology course exercise at Universidad de los Andes, Colombia. This is a teaching/portfolio project, not a validated operational research product.
