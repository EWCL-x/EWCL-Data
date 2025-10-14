# EWCL-Data

Entropy-Weighted Collapse Likelihood (EWCL) benchmark dataset providing per-residue disorder, binding, and collapse metrics across DisProt, MobiDB, IDEAL, CAID, X-ray, NMR, and AlphaFold references using the structure-aware EWCLv1, EWCLv1-p3 models.

## Models

### EWCLv1
EWCLv1 (Entropy-Weighted Collapse Likelihood version 1) is a structure-aware machine learning model that predicts per-residue disorder, binding propensity, and collapse likelihood in proteins. The model incorporates entropy-based features to assess the conformational flexibility and structural disorder of protein residues.

Key features:
- Per-residue disorder predictions
- Binding site probability assessment
- Structural collapse likelihood scoring
- Integration of sequence and structural features

### EWCLv1-p3
EWCLv1-p3 is an enhanced version of the EWCLv1 model with improved performance for predicting protein disorder and binding regions. The "-p3" designation indicates refinements in the prediction algorithm, feature engineering, and training methodology.

Improvements over EWCLv1:
- Enhanced accuracy for disordered region identification
- Better sensitivity for binding site prediction
- Refined entropy-weighting scheme
- Optimized for structural data from multiple sources

## Benchmarks

This dataset includes validation against multiple established protein disorder and structure databases:

### CAID (Critical Assessment of Intrinsic Disorder)
Community-wide assessment for evaluating intrinsic disorder prediction methods. CAID provides experimentally validated disorder annotations for rigorous benchmarking.

### DisProt
Database of intrinsically disordered proteins with manually curated disorder annotations from literature. DisProt entries include experimental evidence for disorder regions.

### MobiDB
A database of protein disorder and mobility annotations, aggregating data from multiple sources including experimental structures and predictions.

### IDEAL
Intrinsically Disordered proteins with Extensive Annotations and Literature. IDEAL provides comprehensive information about intrinsically disordered proteins and their functional annotations.

### X-ray
Protein structures determined by X-ray crystallography from the Protein Data Bank (PDB). These structures provide high-resolution atomic coordinates for disorder analysis.

### NMR
Nuclear Magnetic Resonance spectroscopy-derived protein structures from the PDB. NMR structures often capture conformational heterogeneity and dynamic regions.

### AlphaFold
AI-predicted protein structures from AlphaFold Protein Structure Database. Prediction confidence scores (pLDDT) correlate with structural disorder and flexibility.

## Dataset Structure

```
EWCL-Data/
├── binding/              # Binding site predictions
│   ├── example_binding.csv
│   └── metrics.json
├── disorder_pdb/         # Disorder from PDB structures
│   ├── example_disorder_pdb.csv
│   └── metrics.json
├── disorder_nox/         # Disorder from non-X-ray sources
│   ├── example_disorder_nox.csv
│   └── metrics.json
└── linker/              # Flexible linker regions
    ├── example_linker.csv
    └── metrics.json
```

### Data Format

Each CSV file contains per-residue predictions with the following columns:
- `protein_id`: Unique protein identifier
- `residue_number`: Position in the protein sequence
- `residue_type`: Single-letter amino acid code
- `ewcl_score`: EWCLv1 prediction score
- `ewcl_p3_score`: EWCLv1-p3 prediction score
- Additional columns specific to each dataset category

Each `metrics.json` file provides summary statistics for the corresponding dataset.

## Citation

If you use this dataset, please cite:

**DOI:** [10.5281/zenodo.17352525](https://doi.org/10.5281/zenodo.17352525)

## License

Please refer to the DOI record for licensing information and usage terms.
