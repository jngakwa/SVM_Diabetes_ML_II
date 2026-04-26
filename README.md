# SVM_Diabetes_ML_II

# Predicting Diabetes from Health Behaviors and Demographics Using Support Vector Machines

## Overview
This project uses Support Vector Machine (SVM) models to predict diabetes diagnosis in adults aged 40 and older using data from the 2022 National Health Interview Survey (NHIS), accessed through IPUMS Health Survey.

## Research Question
Can demographic and behavioral survey data predict diabetes diagnosis in adults 40+?

## Data
- **Source:** IPUMS Health Surveys: National Health Interview Survey, Version 7.3
- **Citation:** Blewett LA, Rivera Drew JA, King ML, Williams KCW. IPUMS Health Surveys: National Health Interview Survey, Version 7.3. Minneapolis, MN: IPUMS, 2023. https://doi.org/10.18128/D070.V7.3
- **Population:** Adults aged 40 and older
- **Target Variable:** DIABETICEV (0 = No Diabetes, 1 = Diabetes)

## Predictors
- Age
- BMI
- Smoking status
- Vigorous activity (minutes/day)
- Moderate activity (minutes/day)
- Heart disease history
- Stroke history

## Methods
- Class imbalance addressed via majority class downsampling (balanced 50/50 dataset)
- 80/20 train/test split
- 3-fold cross-validation for all kernels
- Three kernel types compared: linear, radial (RBF), and polynomial

## Results

| Kernel | Test Error | Accuracy |
|---|---|---|
| Linear | 34.8% | 65.2% |
| Polynomial | 34.9% | 65.1% |
| Radial (RBF) | 33.3% | **66.7%** |

The radial kernel performed best. All three kernels produced a diagonal decision boundary where higher BMI combined with older age predicts diabetes.

## Requirements
```r
library(tidyverse)
library(e1071)
```
