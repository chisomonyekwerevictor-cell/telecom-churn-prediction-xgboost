# Telecom Churn Prediction using XGBoost

##  Project Overview
Customer churn is a critical challenge in the telecom industry, where acquiring new customers is significantly more expensive than retaining existing ones.  
This project builds an end-to-end machine learning pipeline to *predict customer churn* using a telecom dataset, with a strong focus on handling *class imbalance* and making *cost-aware classification decisions*.

Rather than relying on accuracy alone, the project prioritizes metrics that matter in real-world churn scenarios, such as *recall, F1-score, and ROC–AUC, and applies **decision threshold tuning* to align predictions with business objectives.

---

##  Business Problem
- *Objective:* Identify customers who are likely to churn.
- *Why it matters:*  
  - False negatives (missed churners) → lost revenue  
  - Early detection enables targeted retention strategies.
- Key challenge:* Churned customers form a minority class, making accuracy a misleading metric.

---

##  Machine Learning Approach
This project follows an *industry-grade ML workflow*, including:

1. Data Audit
   - Dataset structure inspection
   - Missing value analysis
   - Target class distribution analysis
   - Leakage risk checks

2. Preprocessing & Feature Engineering
   - Separation of numeric and categorical features
   - Identification of binary, ordinal, and nominal variables
   - Proper encoding strategies for each type
   - Handling missing values
   - Feature transformations and sanity checks

3. Baseline Modeling
   - Logistic Regression with class weighting used as a baseline
   - Establishes a performance benchmark

4. Imbalanced Learning
   - Class imbalance addressed using scale_pos_weight in XGBoost
   - Prevents bias toward majority (non-churn) class

5. Model Training
   - XGBoost classifier selected for its robustness and ability to model non-linear relationships

6. Model Evaluation
   - ROC–AUC for class separation
   - Precision, recall, and F1-score for detailed performance analysis
   - Accuracy intentionally de-emphasized

7. Decision Threshold Tuning
   - Multiple thresholds evaluated
   - Final threshold selected to *maximize churn recall* while maintaining stability



##  Key Results
- Significant improvement in minority-class (churn) recall
- Balanced trade-off between precision and recall through threshold tuning
- Demonstrates that *model decisions matter as much as model choice*

> The final model favors catching more potential churners, which aligns with real telecom retention strategies.



##  Final Model Configuration
- *Model:* XGBoost Classifier  
- *Imbalance Handling:* scale_pos_weight  
- *Evaluation Metrics:* Recall, F1-score, ROC–AUC  
- *Final Decision Threshold:* 0.35  
- *Primary Goal:* Improve churn detection rather than maximize accuracy  
