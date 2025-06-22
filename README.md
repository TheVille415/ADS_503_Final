# Heart Disease Prediction Using Machine Learning

## Overview

This project aims to develop a predictive model to determine the presence of heart disease in patients based on various medical attributes. Utilizing the UCI Heart Disease dataset, we applied machine learning techniques to analyze patient data and predict heart disease outcomes. Multiple classification models were developed and evaluated to identify the most effective approach for early risk assessment.

## Dataset

- **Source**: [UCI Machine Learning Repository - Heart Disease Dataset](https://archive.ics.uci.edu/dataset/45/heart+disease)
- **Dataset**: `processed.cleveland.data` from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/heart+Disease)
- Records: 303 patient entries
- **Instances**: 303  
- **Attributes**: 14 (including the target variable)  
- **Target Variable**: `num` (0 indicates no presence of heart disease; 1–4 indicate presence)

The dataset includes patient information such as age, sex, chest pain type, resting blood pressure, serum cholesterol, fasting blood sugar, ECG results, max heart rate achieved, ST depression, the slope of the peak ST segment, number of major vessels colored by fluoroscopy, and thalassemia.

## Objective

To build and evaluate machine learning models that accurately predict the presence of heart disease, supporting early diagnosis and clinical decision-making.

## Methodology

1. **Data Preprocessing**:  
   - Converted missing values represented by `?` to `NA`  
   - Imputed missing values (`cp`, `thal`, `ca`) using mode imputation  
   - Normalized numeric features with z-score standardization  
   - Binarized the target into:  
     `0 = No Disease`, `1–4 = Disease`

2. **Exploratory Data Analysis (EDA)**:  
   - Visualized distributions (age, blood pressure, cholesterol, max heart rate)  
   - Correlation heatmaps and boxplots for key predictors

3. **Model Development & Evaluation**:  
   Trained and compared the following classifiers using 70/30 stratified train-test split:
   - Logistic Regression  
   - Decision Tree  
   - Random Forest  
   - Support Vector Machine (SVM)  
   - k-Nearest Neighbors (k-NN)  
   - Gradient Boosting Machine (GBM)

   Models were evaluated using:  
   - Accuracy  
   - Balanced Accuracy  
   - Sensitivity (Recall)  
   - Specificity  
   - Cohen’s Kappa  

## Results

| Model               | Accuracy | Balanced Accuracy | Kappa  | Sensitivity | Specificity |
|--------------------|----------|-------------------|--------|-------------|-------------|
| **k-NN (k = 5)**    | **0.8556** | **0.8514**        | **0.7071** | **0.8980**  | 0.8049      |
| Logistic Regression | 0.8444   | 0.8432            | 0.6864 | 0.8571      | **0.8293**  |
| SVM (Linear)        | 0.8333   | 0.8310            | 0.6633 | 0.8571      | 0.8049      |
| GBM                 | 0.8222   | 0.8208            | 0.6416 | 0.8367      | 0.8049      |
| Random Forest       | 0.8111   | 0.8046            | 0.6154 | 0.8776      | 0.7317      |
| Decision Tree       | 0.7111   | 0.6989            | 0.4058 | 0.8367      | 0.5610      |

The **k-NN classifier with k = 5** outperformed all other models, demonstrating the highest accuracy and balanced accuracy. While logistic regression and SVM showed competitive results, k-NN offered the best trade-off between sensitivity and specificity.

## Team Members

- Saloni Barhate  
- Jordan Torres  

## How to Reproduce

1. Open the R Markdown file: `ADS503_Final.Rmd`  
2. Ensure the data file `processed.cleveland.data` is located in the correct working directory  
3. Knit to HTML or PDF to reproduce all code, visualizations, and performance metrics  

## References

- Detrano, R., Janosi, A., Steinbrunn, W., Pfisterer, M., Schmid, J. J., Sandhu, S., ... & Froelicher, V. (1989). International application of a new probability algorithm for the diagnosis of coronary artery disease. *The American Journal of Cardiology*, 64(5), 304–310.
- Dua, D. & Graff, C. (2019). UCI Machine Learning Repository [https://archive.ics.uci.edu/ml](https://archive.ics.uci.edu/ml)
