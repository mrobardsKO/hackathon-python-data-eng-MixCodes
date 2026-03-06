# hackathon-python-data-eng-MixCodes

COVID-19 country-level testing analysis using Python and Jupyter Notebook.

## Project Objective

This project analyzes global COVID-19 testing data to answer:

**Which countries have reported the highest number of positive cases in relation to the number of tests conducted?**

The notebook performs data loading, cleaning, aggregation, ratio engineering, and visualization to produce ranked country insights.

## Quick Start

Run these commands from the repository root on Windows.

```powershell
# 1) Create virtual environment (skip if .venv already exists)
python -m venv .venv

# 2) Activate environment
.\.venv\Scripts\Activate.ps1

# 3) Install required packages
python -m pip install --upgrade pip
pip install pandas numpy matplotlib seaborn plotly pyarrow jupyter

# 4) Launch Jupyter Notebook
jupyter notebook "COVID19 Worldwide Testing Data.ipynb"
```

If PowerShell blocks activation, run:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

## Repository Structure

- `COVID19 Worldwide Testing Data.ipynb`  
	Main analysis notebook containing tasks 1.1 through 7.3.
- `tested_worldwide.csv`  
	Source dataset used for the analysis.
- `ANALYSIS_CONCLUSIONS.md`  
	Written conclusions, limitations, and next steps (sections 7.1, 7.2, 7.3).
- `LICENSE`  
	GNU GPL v3.
- `README.md`  
	Project documentation.

## Dataset

Input file: `tested_worldwide.csv`

Key fields used in analysis:

- `Date`
- `Country_Region`
- `positive`
- `total_tested`
- `daily_tested`
- `daily_positive`

## Notebook Workflow

The notebook is organized according to the assignment-style steps:

### 1.1 to 1.5 Basic Exploration

1. Load dataset into a DataFrame.
2. Display first rows.
3. Inspect shape and data types.
4. Count missing values.
5. Count unique values per column.

### 2.1 to 2.5 Data Cleaning

1. Drop unneeded columns.
2. Rename columns for clarity.
3. Drop rows missing required analysis values.
4. Convert columns to proper data types.
5. Re-check missing values after cleaning.

### 3.1 to 3.3 Top Countries by Positive Cases

1. Aggregate to country-level total positive cases.
2. Sort descending.
3. Show top 10 countries.

### 4.1 to 4.3 Top Countries by Tests Conducted

1. Aggregate to country-level total tests conducted.
2. Sort descending.
3. Show top 10 countries.

### 5.1 to 5.4 Merge and Ratio Analysis

1. Merge positive and tested country summaries.
2. Compute:
	 - `positive_to_test_ratio = total_positive_cases / total_tests_conducted`
3. Sort descending by ratio.
4. Extract top 3 countries by ratio.

### 6.1 to 6.3 Visualizations

1. Bar chart of top 3 countries by positive-to-test ratio.
2. Bar chart of top 10 countries by total positive cases.
3. Bar chart of top 10 countries by total tests conducted.

### 7.1 to 7.3 Interpretation

1. Conclusions.
2. Limitations.
3. Suggested next steps.

## Core Metrics

- `total_positive_cases`: country-level cumulative positives.
- `total_tests_conducted`: country-level cumulative tests.
- `positive_to_test_ratio`: `total_positive_cases / total_tests_conducted`.

## How to Run

1. Create/activate a Python environment.
2. Install required packages:
	 - `pandas`
	 - `numpy`
	 - `matplotlib`
	 - `seaborn`
	 - `plotly` (optional)
	 - `pyarrow` (optional for parquet export)
3. Open:
	 - `COVID19 Worldwide Testing Data.ipynb`
4. Run cells from top to bottom.

## Expected Outputs

From notebook execution:

1. Country ranking tables:
	 - Top by positive cases
	 - Top by tests conducted
	 - Top by positive-to-test ratio
2. Visualization figures for required tasks.
3. Optional exported outputs (if export cells are enabled).

## Notes on Interpretation

- High positivity ratio can indicate concentrated spread or targeted testing.
- High total tests can reduce ratio while indicating stronger surveillance.
- Rankings should be interpreted with caution due to reporting and policy differences across countries.

## License

This repository is licensed under GNU General Public License v3.0. See `LICENSE` for details.