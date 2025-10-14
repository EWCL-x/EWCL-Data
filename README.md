# EWCL Benchmarks Data (2025)

Entropy-Weighted Collapse Likelihood (EWCL) is a framework for quantifying protein structural disorder, collapse propensity, and binding flexibility through entropy-weighted, structure-aware metrics.

This repository contains benchmark datasets, metrics, and figures generated with the EWCLv1, EWCLv1-p3 models.

## Overview

This dataset provides residue-level predictions, annotations, and performance metrics for EWCL's evaluation across multiple canonical benchmarks.

It serves as a reproducibility resource for the community—enabling fair comparison across methods and datasets assessing thermodynamic disorder and collapse.

## Contents

Each archive (EWCL_*_2025.zip) includes:

- **Per-residue tables**: ewcl_score, amino acids, and reference label
- **Per-protein tables**: ROC-AUC and PR-AUC by UniProt
- **Aggregate metrics**: ROC-AUC, PR-AUC, F1-max in JSON format
- **Figures**: ROC and PR curves, AUC distributions in PNG format

## Benchmarks

| Benchmark | Source | Description |
|-----------|--------|-------------|
| Binding | CAID | IDR-mediated binding disorder benchmark |
| Disorder-PDB | CAID / PDB | Structured vs disordered residues from experimental 3D data |
| Disorder-NOX | CAID | Non-X-ray reference disorder dataset |
| Linker | CAID | Flexible linker region annotations |
| MobiDB | MobiDB | Protein structural disorder annotations |
| AlphaFold | AlphaFold DB | AlphaFold-predicted structures with disorder annotations |
| NMR-Xray | Experimental | NMR and X-ray crystallography experimental references |

## Model Details

EWCL comprises two complementary variants used across these benchmarks:

### EWCLv1 (Sequencer — sequence-only)

- **Inputs**: FASTA only (no structures).
- **Signals**: composition/charge balance, hydropathy, low-complexity/flexibility proxies, short-context motifs.
- **Output**: H_EWCL ∈ [0,1] (higher = broader ensemble) and C_EWCL = 1 − H_EWCL.
- **Purpose**: clean entropy proxy, orthogonal to geometry; ideal for datasets without structures.

### EWCLv1-p3 (Structure-aware)

- **Inputs**: EWCLv1 features + AlphaFold-derived context.
- **Adds**:
  - pLDDT (confidence as a rigidity/consistency proxy)
  - Entropy weighting (hydropathy, charge, flexibility)
  - Curvature/geometry penalties to detect local collapse
- **Purpose**: integrates sequence entropy with 3D confidence to yield a thermodynamic collapse likelihood index.

**Unification**: EWCL models combine sequence-level ensemble propensity with (optionally) structure-based confidence to assess local collapse vs. disorder. Datasets in this release were produced with EWCLv1-p3, while the repo also hosts sequence-only EWCLv1 outputs where applicable/available.

## Benchmarks and References

EWCL Benchmarks draw from multiple curated sources:

- CAID, DisProt, MobiDB, IDEAL
- Experimental references from X-ray crystallography and NMR ensembles
- AlphaFold DB models with disorder annotations

## Citation

If you use these data, please cite:

```
EWCL Research Group (2025).
EWCL Benchmarks Data (2025).
Zenodo. https://doi.org/10.5281/zenodo.17352525
```

## License

CC BY 4.0 International — You are free to use and share this dataset with attribution.

## Related Resources

- EWCL-ready web platform (interactive viewer)
- EWCL API
- EWCL manuscript (preprint, 2025)
