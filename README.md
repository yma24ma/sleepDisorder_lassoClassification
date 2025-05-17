# Predicting Sleep Disorders Using Health and Lifestyle Data with LASSO Logistic Regression

This project uses LASSO Logistic Regression to predict whether an individual is likely to suffer from a sleep disorder based on various health and lifestyle factors. By leveraging penalized logistic modeling and cross-validation, we identify the most relevant predictors and evaluate model performance using ROC and AUC metrics.
This project was completed as part of the STAT301 (Statistical Modeling for Data Science) course at The University of British Columbia.

---

## Tools & Technologies

- **R (tidyverse, glmnet, caret, pROC, boot)**: Data processing, modeling, and evaluation  
- **Sleep Health and Lifestyle Dataset**: 374 observations with 13 health-related variables  
- **LASSO (Least Absolute Shrinkage and Selection Operator)**: For variable selection and model regularization  
- **10-Fold Cross-Validation**: For optimal lambda (λ) selection  
- **ROC Curve & AUC**: For classifier performance evaluation  
- **ggplot2**: For data visualization and interpretation

---

## What the Project Does

- **Data Cleaning & Preprocessing**:
  - Converted variable names to `snake_case`
  - Split `blood_pressure` into `systolic_bp` and `diastolic_bp`
  - Categorized BMI and binary-encoded the `sleep_disorder` variable

- **Model Formation**:
  - Applied LASSO logistic regression to select significant predictors
  - Used 10-fold CV to determine optimal lambda (1SE rule used for generalization)

- **Model Evaluation**:
  - Evaluated model on a 40% test set
  - Generated ROC curve and computed AUC to assess classification performance

- **Final Predictors**:
  - `bmi_categoryOverweight`
  - `diastolic_bp`

---

## Model Performance

![ROC](https://github.com/user-attachments/assets/245a39d5-af0d-460e-a76b-1dac7a8eb36b)

| Metric | Score   |
|--------|---------|
| AUC    | **0.9553**  |

> AUC of 0.9553 indicates excellent predictive performance and strong ability to distinguish between those with and without sleep disorders.

---


## Limitations and Future Improvements

While the model performed strongly, there are limitations and areas for future research:

- **Small sample size**: Limits model generalizability and reduces the statistical power
- **Variable exclusion**: Stress level, sleep duration, and physical activity were not retained due to potential multicollinearity or data sparsity
- **Imbalanced categories**: Low representation of “obese” may have impacted LASSO’s ability to retain it
- **Model bias**: LASSO introduces bias by shrinking coefficients

---

## Future Directions

- Use a **larger and more balanced dataset** for better generalizability
- Experiment with **alternative selection criteria** (e.g., minimum AUC)
- Include **interaction terms** or nonlinear transformations
- Try **tree-based models** like Random Forest or Gradient Boosting for better performance
- Integrate **real-time wearable data** for more dynamic prediction

---

## Contributors

- Yuki Matsushima (#84356377)  
- Masaya Tanaka (#59477232)  
- Aryan Arora (#81663510)

---

## Disclaimer

This project was conducted as part of the STAT301 course at the University of British Columbia for educational purposes only. It is not intended for clinical or diagnostic use.
