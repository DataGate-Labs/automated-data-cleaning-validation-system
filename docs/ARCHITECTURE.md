# System Architecture

## Overview

The Automated Data Cleaning and Validation System follows a modular architecture. Each module is responsible for a single task, making the system easy to understand, maintain, and extend.

The processing pipeline flows sequentially from data ingestion to report generation.

---

# High-Level Architecture

Input Dataset
↓
Data Ingestion
↓
Data Profiling
↓
Data Cleaning
↓
Data Validation
↓
Anomaly Detection
↓
Report Generation
↓
Output

---

## Module 1 — Data Ingestion

### Responsibility

Accept datasets from different file formats and load them into a common internal structure.

### Input

- CSV
- Excel (.xlsx)
- JSON

### Output

- Pandas DataFrame

---

## Module 2 — Data Profiling

### Responsibility

Analyze the dataset and generate statistics before cleaning.

### Tasks

- Dataset dimensions
- Missing values
- Duplicate rows
- Data types
- Unique values
- Null percentage
- Summary statistics

### Output

profiling_report.json

---

## Module 3 — Data Cleaning

### Responsibility

Improve dataset quality.

### Tasks

- Remove duplicates
- Handle missing values
- Standardize formats
- Fix inconsistent values
- Remove unnecessary whitespace
- Convert data types

### Output

cleaned_data.csv

cleaning_log.json

---

## Module 4 — Data Validation

### Responsibility

Verify that cleaned data satisfies quality rules.

### Validation Examples

- Required fields
- Valid ranges
- Valid dates
- Allowed categories
- Duplicate verification

### Output

validation_report.json

---

## Module 5 — Anomaly Detection

### Responsibility

Identify unusual records that may require manual review.

### Possible Techniques

- Z-score
- IQR
- Isolation Forest (future enhancement)

### Output

anomaly_report.json

---

## Module 6 — Report Generation

### Responsibility

Generate final reports summarizing the processing pipeline.

### Reports

- Profiling Report
- Cleaning Log
- Validation Report
- Anomaly Report

---

# Technology Stack

Programming Language

- Python 3.12+

Core Libraries

- Pandas
- NumPy

Data Validation

- Great Expectations (to be evaluated)

Machine Learning

- Scikit-learn

Testing

- Pytest

Documentation

- Markdown

Version Control

- Git
- GitHub

---

# Design Principles

- Modular architecture
- Reusable components
- Configurable cleaning rules
- Extensible validation framework
- Maintainable codebase
- Clear separation of responsibilities
