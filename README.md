#**Project Summary**
---

This project satisfies the Advanced Machine Learning Summative Evaluation guidelines for Category 1: Anomaly Detection in Financial Transactions. It deploys a leak-proof analytics architecture to identify hidden fraud vectors under severe class imbalances.

###**Methodological Architecture**
---

**Unsupervised Outlier Profiling**: Implemented an Isolation Forest model optimized across scaled transaction matrices to isolate anomalous records on the margins of geometric coordinate spaces.

**Hybrid Boundary Resampling**: Leveraged a sequential step pairing Synthetic Minority Over-sampling (SMOTE) at a structured 0.05 index with Tomek Links boundary deletion to eliminate overlapping noise between transaction vectors.

**Hyperparameter Grid Search**: Evaluated a 48-fold cross-validation matrix (GridSearchCV) targeting L2 regularization scales and depth parameters to optimize the model specifically for Area Under the Precision-Recall Curve (PR-AUC).

###**Core Engineering Results**
---

### **TECHNIQUE 1: UNSUPERVISED ISOLATION FOREST RESULTS**

```text
              precision    recall  f1-score   support

  Legitimate       1.00      1.00      1.00     56864
       Fraud       0.32      0.33      0.32        98

    accuracy                           1.00     56962
   macro avg       0.66      0.66      0.66     56962
weighted avg       1.00      1.00      1.00     56962
```

Isolation Forest Baseline PR-AUC: 0.1056

```text
**TECHNIQUE 2: GRIDSEARCH TUNED GRADIENT BOOSTING + SMOTE**
              precision    recall  f1-score   support

  Legitimate       1.00      1.00      1.00     56864
       Fraud       0.97      0.87      0.91        98

    accuracy                           1.00     56962
   macro avg       0.98      0.93      0.96     56962
weighted avg       1.00      1.00      1.00     56962
```

Supervised Engine Optimized PR-AUC: 0.8945

Selected Optimal Hyperparameters: 
```python
{'classifier__l2_regularization': 1.0, 'classifier__learning_rate': 0.1, 'classifier__max_depth': 6, 'classifier__max_iter': 150}
```
