# Breast Cancer Gene Expression Analysis

## Overview
A Python bioinformatics project comparing gene expression between
breast tumor and normal breast tissue using GEO dataset GSE70905.

## Objective
Identify probes with statistically significant expression differences
between matched tumor and normal samples.

## Dataset
- Source: [NCBI Gene Expression Omnibus — GSE70905](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE70905)
- Technology: Microarray
- Probes analyzed: 10
- Matched patient pairs: 47

## Methods
1. Loaded the processed gene-expression matrix.
2. Matched normal and tumor samples using patient identifiers.
3. Performed paired t-tests for each probe.
4. Applied Benjamini-Hochberg false discovery rate correction.
5. Annotated probes using the platform annotation file.
6. Visualized the results using a volcano plot and heatmap.

## Results
- Probes tested: 10
- Significant probes (FDR < 0.05): 20,246
- Higher expression in tumor (positive difference): 10,466
- Lower expression in tumor (negative difference): 9,780

A positive difference means higher average expression in tumor samples.
A negative difference means lower average expression in tumor samples.
Differences are measured on the supplied expression scale, not as fold changes.

## Top 10 Significant Probes

| Probe ID | Gene Symbol | Tumor - Normal Difference | FDR |
|---|---|---:|---:|
| 19252 | SSB | 1.515 | 2.01e-19 |
| 11952 | KIAA1609 | -1.061 | 2.01e-19 |
| 27034 | ANKRD10 | -1.875 | 2.01e-19 |
| 11354 | NTAN1 | -0.979 | 2.01e-19 |
| 16294 | GAGE7 | -1.746 | 2.91e-19 |
| 25086 | CXCL5 | -4.112 | 4.39e-19 |
| 18934 | Unannotated | -2.341 | 6.38e-19 |
| 16900 | Unannotated | -1.855 | 1.90e-18 |
| 3977 | Unannotated | -1.903 | 2.62e-18 |
| 20214 | DUSP9 | -2.543 | 2.62e-18 |

## Output Files
- `result/limma_free_python_results.csv` — results for all probes.
- `result/significant_genes_python.csv` — statistically significant probes.
- `result/top_10_significant_probes.csv` — top 10 ranked probes.
- `result/heatmap_top30_probes.png` — expression heatmap.

## Tools
Python, Pandas, NumPy, SciPy, Statsmodels, Matplotlib, and Jupyter Notebook.

## Limitations
- Some probes may not have gene annotations.
- Multiple probes may map to the same gene.
- Statistical associations do not establish causation.
- The findings require independent validation before biological or clinical conclusions.

## Reproducibility
The analysis notebook is `note book/breastcancer.ipynb`.
The notebook requires the dataset and annotation files used in this project.
