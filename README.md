# Air_Quality_Monitoring
Air quality dataset preprocessed for Weka. Contains pollutant levels and location data. Ready for machine learning: forecasting, clustering, and classification. Jumpstart your environmental ML projects.
# Kaggle Dataset (Preprocessed for Weka)

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


