# Programming of AI (POAI) Assignment

## Overview
This repository contains the Jupyter notebook `POAI-ASSIGNMENT.ipynb`, which implements solutions for an assignment in Programming of AI, submitted by Muhammad Sami (Roll No: 22F-BSAI-43) under the supervision of Sir Hamza Farooqui. The notebook focuses on data preprocessing, statistical analysis, data visualization, and modeling a differential equation for medication concentration in blood.

## Contents
The notebook is divided into two main questions:

### Q1: Outlier Detection and Feature Reduction
This section processes a patient dataset (`patient_data.csv`) to clean and prepare it for analysis:
- **Data Loading**: Reads the dataset using pandas.
- **Feature Selection**: Uses `VarianceThreshold` from scikit-learn to remove low-variance numeric features.
- **Outlier Removal**: Applies z-score filtering to remove outliers in the `CholesterolLevel` column (z-score > 3).
- **Missing Value Handling**: Fills missing values in numeric columns with their means.
- **Output**: Displays the first five rows of the cleaned dataset.

### Q2: Data Visualization
This section visualizes the processed dataset:
- **Boxplot**: Displays the distribution of `BloodPressure` across `RiskCategory` using seaborn's `boxplot`.
- **Countplot**: Shows the count of patients by `Region` and `RiskCategory` using seaborn's `countplot`.
- **Differential Equation Plot**: Models medication concentration in blood over time using a first-order differential equation. Solves it using both `odeint` and `solve_ivp` from `scipy.integrate`, then plots the results with matplotlib for comparison.

### Statistical Analysis
Additional statistical tests are performed:
- **One-Sample T-Test**: Tests if the mean of a random sample of 20 `CholesterolLevel` values differs significantly from 200 (hypothesized mean).
- **Chi-Square Test**: Examines the independence between `Region` and `RiskCategory` using a contingency table.

## Requirements
To run the notebook, install the following Python packages:
```bash
pip install pandas numpy scikit-learn scipy seaborn matplotlib
```

## Dataset
The notebook assumes the presence of a `patient_data.csv` file with the following columns:
- `PatientID`
- `Age`
- `CholesterolLevel`
- `BloodPressure`
- `Gender`
- `Region`
- `RiskCategory`

Ensure this file is in the same directory as the notebook or update the file path accordingly.

## Usage
1. Clone this repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the repository directory:
   ```bash
   cd <repository-name>
   ```
3. Install the required dependencies (see above).
4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook POAI-ASSIGNMENT.ipynb
   ```
5. Run the cells in sequence to execute the data processing, visualization, and modeling tasks.

## Output
- **Q1**: A cleaned DataFrame with low-variance features and outliers removed, displayed as a table.
- **Q2**: Two plots (boxplot and countplot) and a comparison plot of medication concentration using `odeint` and `solve_ivp`.
- **Statistical Tests**: T-test and chi-square test results, including test statistics, p-values, and hypothesis test conclusions.

## Notes
- The code is written in Python 3.13.3 and tested in a Jupyter Notebook environment.
- Ensure the `patient_data.csv` file is available to avoid file-not-found errors.
- The differential equation modeling assumes constants `k=0.1`, `D=100`, and initial condition `C0=0`.

## Author
- **Name**: Muhammad Sami
- **Roll No**: 22F-BSAI-43
- **Submitted to**: Sir Hamza Farooqui

Feel free to explore the code and adapt it for further analysis!