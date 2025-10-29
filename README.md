# Strike Prediction Model

This project builds a machine learning model to predict whether a baseball pitch will be called a **strike** or a **ball** based on pitch-level data.  
It uses structured features such as pitch location, movement, release speed, and count context, and applies an **XGBoost Classifier** to model nonlinear relationships within the strike zone.

---

## Overview

The goal of this project is to analyze and predict umpire strike calls using cleaned and engineered features from a baseball pitch dataset.  
The final model achieves **~75.8% accuracy** with balanced precision and recall, showing strong generalization on test data.

---

## Key Steps

1. **Data Cleaning** – Removes outliers and invalid pitch records based on physical constraints (release speed, location, etc.).  
2. **Feature Engineering** – Adds derived features such as:
   - `is_in_zone`: identifies if a pitch is inside the strike zone  
   - `in_shadow_zone`: flags borderline pitches  
   - `count_encoded`: encodes the count (balls-strikes) interaction  
3. **Model Training** – Trains an **XGBoost classifier** with cross-validation and tuned hyperparameters.  
4. **Evaluation** – Uses accuracy, precision, recall, F1-score, and confusion matrix to assess performance.

---

## Results

- **Accuracy:** 75.8%  
- **Precision:** 0.70  
- **Recall:** 0.72  
- **F1 Score:** 0.71  
- Key predictors: `is_in_zone`, count-based features, and pitch location.

