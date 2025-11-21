# Protein Chromatography Analysis

This repository contains Jupyter notebooks for analyzing protein chromatography datasets, focusing on IMAC and SEC workflows. The notebooks read instrument-exported CSV files, extract key series, and generate publication-quality plots.

## Contents
- `IMACanalysis.ipynb`: IMAC run analysis with UV280 and buffer B concentration; supports fraction markers and saves plots as JPG.
- `SECanalysis.ipynb`: SEC run analysis with UV280 and conductivity; supports fraction markers and saves plots as JPG.

## Features
- Auto-detects the single CSV file in the working folder.
- Detects and handles file encoding robustly.
- Extracts data series (e.g., `UV_280`, `Cond`, `Conc_B`, and `UV_280_CUT` where applicable).
- Renders fraction collection markers and labels along the x-axis.
- Saves high-resolution figures (`.jpg`) alongside the input CSV.

## Requirements
- Python 3.x
- Packages: `pandas`, `matplotlib`, `chardet`

Install packages:
```
pip install pandas matplotlib chardet
```

## Usage
1. Place the target CSV and the notebook in the same folder. Ensure there is exactly one CSV in that folder.
2. Open the notebook in Jupyter and run all cells.
3. Outputs:
   - IMAC: generates `<input>.jpg` and `<input>_Fracs.jpg` plots.
   - SEC: generates `<input>.jpg` plot.

## Notes
- CSVs are expected to be tab-separated with specific column positions for volume and values; the notebooks handle index resetting and NaN cleanup.
- Fraction labels are selectively displayed to avoid overlap.