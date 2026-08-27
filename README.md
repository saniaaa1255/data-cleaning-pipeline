# Real-World Data Cleaning Pipeline

## Overview
This project takes a messy, uncleaned real-world dataset and transforms it into an analysable, clean, and reproducible format using Python and pandas. The entire data cleaning pipeline runs end-to-end automatically.

---

## Project Structure
```text
├── data/
│   ├── raw_dataset.csv       # The original uncleaned raw data
│   └── clean_dataset.csv     # The final processed and cleaned data
├── clean_pipeline.py         # The reproducible Python cleaning script
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation

Data Quality Issues Addressed
The raw dataset contained the following real-world anomalies:
Duplicate Rows: Exact duplicate entries that would skew analysis.
Missing Values: Blank cells in critical identifier columns and numerical features.
Inconsistent Categories: Variations in casing and text formats.
Mixed Date Formats: Irregularly formatted date strings.
Cleaning Decisions & Justifications
Dropped Duplicate Rows: Removed identical records using df.drop_duplicates() to prevent artificial bias and data leakage.
Handled Missing Critical IDs: Dropped rows where essential unique identifiers were missing because records lacking primary keys cannot be reliably tracked or imputed.
Numerical Imputation: Filled missing values in numerical columns using the median to prevent distortion from extreme outliers.
Standardized Text and Dates: Trimmed whitespaces, forced consistent casing, and safely parsed dates using pd.to_datetime(..., errors='coerce').
