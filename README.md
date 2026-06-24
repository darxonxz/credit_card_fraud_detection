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

  Legitimate       1.00      1.00      1.00     56651
       Fraud       0.18      0.16      0.17        95

    accuracy                           1.00     56746
   macro avg       0.59      0.58      0.58     56746
weighted avg       1.00      1.00      1.00     56746
```

Isolation Forest Baseline PR-AUC: 0.0296

```text
**TECHNIQUE 2: GRIDSEARCH TUNED GRADIENT BOOSTING + SMOTE**
              precision    recall  f1-score   support
  Legitimate       1.00      1.00      1.00     56651
       Fraud       0.92      0.77      0.84        95

    accuracy                           1.00     56746
   macro avg       0.96      0.88      0.92     56746
weighted avg       1.00      1.00      1.00     56746
```
Supervised Engine Optimized PR-AUC: 0.8162

```python
Selected Optimal Hyperparameters: {'classifier__l2_regularization': 5.0, 'classifier__learning_rate': 0.1, 'classifier__max_depth': 6, 'classifier__max_iter': 150}
```
