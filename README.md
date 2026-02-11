# Customer Churn Prediction – Applied Machine Learning Project

## Project Overview

This project develops a machine learning model to predict customer churn (service abandonment) in order to identify high-risk clients and support proactive retention strategies.

The focus of this project is not only predictive performance, but alignment between model selection and business impact.

---

## Business Objective

The objective is to detect customers likely to churn (churn = 1) to:

- Reduce revenue loss  
- Improve retention campaigns  
- Prioritize intervention efforts  

Given that failing to detect a churn case can be costly, the primary optimization metric is:

**Recall for the churn class (1)**

This ensures that the model maximizes identification of customers at risk.

---

## Dataset Description

The dataset simulates a telecom-like environment and includes the following variables:

- `tenure_months`: Customer lifetime with the company  
- `monthly_fee`: Monthly subscription cost  
- `total_usage_hours`: Total usage of service  
- `num_support_tickets`: Number of support interactions  
- `contract_type`: Monthly or annual contract  
- `has_discount`: Discount indicator  
- `churn`: Target variable (0 = stays, 1 = leaves)  

---

## Exploratory Data Analysis

Key observations:

- Churn rate is approximately 56%.  
- Monthly fee shows a positive correlation with churn.  
- Churn behavior appears driven by a combination of variables rather than a single dominant factor.  
- Contract type and pricing structure influence churn distribution.  

The analysis suggests interaction effects between pricing, tenure, and contract conditions.

---

## Data Preparation

The following preprocessing steps were applied:

- One-Hot Encoding for categorical variables  
- MinMax scaling for numerical features  
- Train/Test split (80/20)  

This ensured consistent feature scaling and proper model evaluation.

---

## Models Evaluated

The following classification models were implemented:

- Logistic Regression  
- K-Nearest Neighbors (KNN)  
- Random Forest  
- XGBoost  

Each model was evaluated using:

- Classification Report  
- Confusion Matrix  
- ROC-AUC Score  

The primary evaluation criterion was recall for churn (class 1).

---

## Final Model Selection

The base Random Forest model was selected as the final model.

Although hyperparameter tuning was performed using GridSearchCV, the tuned model showed reduced recall for churn cases on the test set.

Since the business objective prioritizes detecting churn (minimizing false negatives), the base Random Forest model demonstrated better operational alignment due to its higher recall for the churn class.

This reflects a deliberate trade-off between overall balance and churn detection sensitivity.

---

## Hyperparameter Tuning

GridSearchCV was applied to explore different parameter combinations for Random Forest.

While cross-validation performance improved in weighted metrics, churn recall decreased compared to the base model.

This highlights the importance of aligning model selection with business-driven metrics rather than relying solely on cross-validation optimization.

---

## Key Insights

- Monthly fee is one of the strongest drivers of churn.  
- Churn is influenced by interaction between tenure, pricing, and contract structure.  
- Discounts alone do not guarantee churn reduction.  
- Over-regularized models may reduce sensitivity to churn cases.  

---

## Business Implications

Customers with the following characteristics present higher churn risk:

- High monthly fees  
- Short tenure  
- Monthly contracts  

Targeted retention strategies focused on these segments could reduce revenue loss and improve customer lifetime value.

---

## Skills Demonstrated

- End-to-end machine learning pipeline  
- Business-driven metric selection  
- Model comparison and evaluation  
- Hyperparameter tuning  
- Trade-off analysis  
- Applied decision-making in model selection  

---

## Future Improvements

- Threshold optimization for churn prioritization  
- Probability calibration  
- SHAP-based interpretability  
- Deployment as an interactive application (e.g., Streamlit)  

---

## Author

Luis Eduardo Flores Zuazo  
Industrial Engineering – University of Arizona  
Information Systems Engineering – UPC  

Focus: Applied Artificial Intelligence for business decision-making.
