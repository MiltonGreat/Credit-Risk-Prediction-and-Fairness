# Credit Risk Prediction and Fairness Evaluation

## Overview

This project focuses on developing a predictive model for assessing credit risk using the German Credit Data dataset and evaluating the fairness of the model's predictions. The model aims to predict whether clients are at high or low credit risk based on their personal and financial characteristics.

### Data

The dataset used in this project is the German Credit Data, which contains information on 1000 clients and their credit risk status. The dataset includes both numerical and categorical variables such as:

- Age: Age of the client.
- Job: Type of job the client holds.
- Credit Amount: The amount of credit requested.
- Duration: Duration of the credit request in months.
- Housing: Whether the client owns or rents a house.
- Purpose: Purpose of the credit (e.g., education, car, repairs).

##### Target Variable:

- Credit Risk: A binary variable where 1 represents high credit risk and 0 represents low credit risk.

### Modeling Approach

The following machine learning algorithms were evaluated for predicting credit risk:

- LightGBM: Achieved the highest accuracy and a well-balanced precision-recall tradeoff.
- XGBoost: Performed similarly to LightGBM, making it a strong alternative.
- Random Forest: Outperformed Decision Tree, proving that ensemble methods improve model performance.
- Decision Tree: Struggled to capture complex patterns, resulting in the lowest accuracy.

#### Data Preprocessing Steps:
- Weighted class balancing to address the class imbalance in the target variable.
- Encoding categorical features (e.g., job type, housing status).
- Handling missing values where applicable.

#### Hyperparameters Tuning:
- The models were tuned using grid search to optimize their performance.

### Fairness Evaluation

The model's fairness was assessed by evaluating the following:

#### Accuracy Disparity:
- Males: 79.3% accuracy.
- Females: 68.3% accuracy.
- A gap of approximately 11% suggests potential bias favoring males in the predictions.

#### Disparate Impact:
- A ratio of 1.16 between the positive prediction rates for males and females, indicating mild disparities.

#### Feature Importance Disparity:
- Males: More influenced by Housing, Job, and Duration.
- Females: More influenced by Age and Saving accounts.

### Results

- Model Performance: LightGBM achieved the highest accuracy (76%) and balanced precision-recall tradeoff.
- Fairness Issues: There was a significant accuracy disparity between males and females, suggesting potential bias in the model's predictions.
- Feature Importance: Males and females were influenced by different features, with housing and job-related features having a higher impact on males, while age and savings were more influential for females.

## Conclusions

While the model performs well overall, there are disparities in performance based on gender. Males have a higher prediction accuracy than females, and certain features impact different genders differently. To address these fairness issues, further techniques such as bias correction or fairness-aware modeling could be employed. This would help ensure that the model's predictions are equitable across demographic groups.

### Source

https://www.kaggle.com/datasets/varunchawla30/german-credit-data
