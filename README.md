# Air_Quality_Monitoring

# Week 1 – Dataset Selection, Preprocessing, Visualization

Air quality dataset preprocessed for Weka. Contains pollutant levels and location data. Ready for machine learning: forecasting, clustering, and classification. Jumpstart your environmental ML projects.

## Kaggle Dataset (Preprocessed for Weka)

This repository contains a dataset originally sourced from Kaggle, preprocessed and converted into **ARFF format** for use with [Weka](https://www.cs.waikato.ac.nz/ml/weka/).

## Files

- **dataset_preprocessed.arff**  
  The cleaned dataset in ARFF format, ready to be loaded into Weka.

- **preprocessing_report.txt**  
  A summary of preprocessing steps applied (columns dropped, missing values imputed, scaling, etc.).

## Preprocessing Summary

- Dropped fully-empty, constant, and ID-like columns.  
- Imputed missing values:  
  - Numeric → median  
  - Categorical → mode  
  - High-cardinality text → `"missing"`  
- Normalized numeric features to [0,1].  
- Exported categorical columns as **nominal** if unique values are few; otherwise stored as **string**.

## Usage

1. Open Weka → *Explorer* → *Preprocess* tab.  
2. Load the file `dataset_preprocessed.arff`.  
3. Continue with your machine learning workflow (classification, clustering, etc.).

## Notes
- This preprocessing is a general-purpose pipeline. Depending on your ML task, you may wish to adjust:  
  - Feature selection/removal  
  - Scaling method (e.g., `Standardize` instead of `Normalize`)  
  - Encoding of categorical variables  


---

# Week 2 – Model Implementation and Evaluation
---
## 📌 Task Overview
In this week’s task, we focused on **implementing machine learning models** on the preprocessed Air Quality dataset and **evaluating their performance**.  
The goal is to identify which model works best for predicting the chosen target variable (e.g., `pollutant_avg`, `AQI`, etc.).

---

## ⚙️ Steps Performed
1. **Dataset Loading**
   - Used the preprocessed dataset (`.csv`) from Week 1.
   - Inspected columns and dataset shape.

2. **Target Selection**
   - Defined the column to predict (target variable).
   - Example: `pollutant_avg`, `AQI`, or `pollutant_max`.

3. **Problem Type Detection**
   - If the target is continuous → **Regression task**.
   - If the target has a small set of categories → **Classification task**.

4. **Feature Preparation**
   - Removed the target column from features.
   - Used numeric columns as features (categorical encoding can be added later).
   - Filled missing numeric values with median.

5. **Model Training**
   - For **Regression**:
     - `LinearRegression`
     - `RandomForestRegressor`
     - `GradientBoostingRegressor`
   - For **Classification**:
     - `LogisticRegression`
     - `RandomForestClassifier`
     - `GradientBoostingClassifier`

6. **Evaluation Metrics**
   - **Regression:** MAE, RMSE, R² score.
   - **Classification:** Accuracy, F1-score, Confusion Matrix.

7. **Model Selection**
   - Chose the **best model** based on highest R² (regression) or accuracy (classification).
   - Saved the trained best model as `best_model.pkl`.

8. **Visualization**
   - Scatter plot of true vs predicted (regression).
   - Confusion matrix heatmap (classification).
   - Feature importance (if supported by the model).

---
## Outputs

•	Prints training results for all models.

•	Displays plots (scatter plot, confusion matrix, feature importance).

•	Saves the best model as:
best_model.pkl

---

## ✅ Deliverables for Week 2
1.	Air pollution monitoring using machine learning.ipynb → updated script for model implementation & evaluation.
2.	best_model.pkl → saved trained model.
3.	README.md → updated this documentation file.

---


