# Admission metabolic factors and futile recanalisation after thrombectomy: analysis code

Author: Max Brzezicki, Department of Neural Engineering and Space Medicine, University of Zielona Góra.

## Contents

- `Glucose_thrombectomy_analysis.ipynb`: the complete analysis, saved with the outputs of the run that produced the manuscript.
- `outputs/results/`: every aggregate table as CSV, and `results_manifest.json`, which registers every number reported in the manuscript, the Supplementary Information and the figure legends, with its rounding, the package versions, the SHA-256 of both data files, the seed and the printed size of each figure. Per-patient result files are not included.
- `outputs/figs/`: Figures 1 to 5 and Supplementary Figures S1 to S5 as PNG (600 dpi) and PDF.
- `requirements.txt`: the pinned environment.
- `data/README.md`: description of the two patient-level input files.

## Data

The patient-level data are not publicly available because they contain pseudonymised clinical data collected under the General Data Protection Regulation. They are available from the corresponding author on reasonable request under a data-use agreement. With the two files placed in `data/`, the notebook reproduces every reported value.

## To reproduce

Python 3.12. From the repository root, with the data files in `data/`:

    python3 -m venv venv && . venv/bin/activate
    pip install -r requirements.txt
    python -m ipykernel install --user --name python3
    jupyter-execute --inplace Glucose_thrombectomy_analysis.ipynb

One fixed seed (20260719) governs every stochastic step, so a rerun reproduces every value in the manifest and every figure exactly. The SHA-256 of each data file is recorded in `outputs/results/results_manifest.json` under `_provenance`, so a user of the data can confirm that the files match those analysed.
