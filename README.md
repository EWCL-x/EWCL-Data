# EWCL-Data

[![DOI – MobiDB/DisProt benchmarks](https://zenodo.org/badge/DOI/10.5281/zenodo.17409146.svg)](https://doi.org/10.5281/zenodo.17409146)
[![DOI – CAID-aligned benchmarks](https://zenodo.org/badge/DOI/10.5281/zenodo.17352525.svg)](https://doi.org/10.5281/zenodo.17352525)

Entropy-Weighted Collapse Likelihood (**EWCL**) benchmark data supporting

> *Cristino & Uversky, “Entropy-Weighted Collapse Likelihood: Putting Ensemble Thermodynamics First in Disorder Characterization”, Biomolecules (submitted).*

This repository provides a landing page, light-weight manifests, and example scripts.  
The **heavy per-residue CSV/JSON outputs** are archived on Zenodo (see below).

---

## Archived datasets

### 1. MobiDB / DisProt, IDEAL, Merge, UniProt & binding snapshots

**Zenodo record (primary benchmark archive)**  
🔗 https://doi.org/10.5281/zenodo.17409146  

Contents (per-residue, frozen):

- DisProt, IDEAL, Merge, and curated UniProt references  
- Binding-related snapshots (e.g. FuzPred, FuzDrop, AIUPred comparisons)  
- EWCLv1 scores and labels used for all tables/figures in the paper  

All files here are exactly the ones referenced in the manuscript tables and figure panels.

---

### 2. CAID-aligned benchmarks (PDB & NOX tracks, linker, binding)

**Zenodo record (CAID-aligned archive)**  
🔗 https://doi.org/10.5281/zenodo.17352525  

Contents:

- CAID-aligned disorder, linker, and binding benchmarks  
- EWCLv1 per-residue scores and labels on CAID reference sets  
- Metrics used for the “CAID-aligned” comparison tables in the manuscript  

These data are *alignment only* and are **not** a CAID leaderboard submission.

---

### 3. NMR, X-ray, and AlphaFold overlays

Planned archives (links will be added when the Zenodo records are public):

- **NMR rigidity benchmark** – EWCL vs per-residue rigidity traces  
- **X-ray B-factor benchmark** – EWCL vs SIFTS-normalized B-factors  
- **AlphaFold overlays** – EWCL-P3 vs pLDDT and hallucination masks  

Until those are live, the corresponding figures in the manuscript are generated
from a frozen internal snapshot of these datasets.

---

## Repository contents

This GitHub repo is intentionally light-weight:

- `README.md` – this file, with links to all Zenodo archives  
- (Optional) `manifests/` – text/CSV manifests listing which files are in each Zenodo record  
- `examples/` – minimal examples showing how to:
  - load the per-residue CSV/JSON files
  - compute AUROC / AUPRC
  - recreate simple EWCL vs DisProt or EWCL vs pLDDT plots

**Note:** The full benchmark CSV/JSON files themselves are stored on Zenodo,  
not committed here, to keep the repository small and versioned cleanly.

---

## Frontend / API

The same frozen per-residue outputs are also exposed in read-only form through:

- 🌐 EWCLx frontend: https://ewclx.com  

When a given protein is available both in the Zenodo archives and on EWCLx, the
overlays and metrics shown on the site are generated directly from the archived
per-residue scores.

---

## How to cite

If you use these benchmarks or overlays, please cite:

**EWCL benchmark datasets (MobiDB/DisProt, IDEAL, Merge, UniProt, binding)**  
> Cristino, L.; Uversky, V.N. (2025). *EWCL – MobiDB/DisProt, IDEAL, Merge, UniProt, and Binding Benchmarks* (Version 1). Zenodo. https://doi.org/10.5281/zenodo.17409146  

**EWCL – CAID-aligned benchmarks**  
> Cristino, L.; Uversky, V.N. (2025). *EWCL – CAID-aligned Benchmarks (Disorder PDB & NOX, Linker, Binding)* (Version 1). Zenodo. https://doi.org/10.5281/zenodo.17352525  

BibTeX:

```bibtex
@dataset{ewcl_mobidb_zenodo_2025,
  author    = {Lucas Cristino and Vladimir N. Uversky},
  title     = {EWCL -- MobiDB/DisProt, IDEAL, Merge, UniProt, and Binding Benchmarks},
  year      = {2025},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.17409146},
  url       = {https://doi.org/10.5281/zenodo.17409146}
}

@dataset{ewcl_caid_zenodo_2025,
  author    = {Lucas Cristino and Vladimir N. Uversky},
  title     = {EWCL -- CAID-aligned Benchmarks (Disorder PDB \& NOX, Linker, Binding)},
  year      = {2025},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.17352525},
  url       = {https://doi.org/10.5281/zenodo.17352525}
}
