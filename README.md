**Problem Statement**

In clinical diagnostics, the manual classification of tumors as Malignant (cancerous) or Benign (non-cancerous) is a time-consuming process prone to human error. The goal of this project is to develop a robust machine learning pipeline that can automate this classification using the Breast Cancer Wisconsin (Diagnostic) Dataset.

**Dataset Used**: https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data

**Solution**

**Technical Approach Used**: Linear Support Vector Machine (SVM) with automated preprocessing.

To solve the classification problem, I implemented a Support Vector Machine (SVM) using a Linear Kernel.

SVM was chosen because of its effectiveness in finding the "Optimal Hyperplane" that maximizes the margin (the safety buffer) between classes.

**Key Implementation Details**:

**Pipeline Architecture**: Utilized a Scikit-Learn Pipeline to bundle StandardScaler and the SVC model. 
                           This ensures that the data scaling is performed correctly within each fold of cross-validation, preventing data leakage.
                           
**Hyperparameter Tuning**: Optimized the C hyperparameter 1. This "Soft Margin" approach improved the model's ability to generalize to new, unseen patient data by prioritizing a wider decision boundary over perfect memorization of training noise.

**Evaluation Strategy**: Beyond simple accuracy, the model was evaluated using:

**5-Fold Cross-Validation**: To ensure stability across different data distributions.
                         
**Confusion Matrix Analysis**: Specifically monitoring False Negatives to evaluate clinical safety.

**Results and Impact**:

The optimized SVM model achieved a Mean Cross-Validation Accuracy of 97.19%, with a specific test set performance of 99.12%.

**Final Performance Metrics**:

**True Negatives**: 71 (Benign correctly identified)

**True Positives**: 42 (Malignant correctly identified)

**False Positives**: 0 (Zero healthy patients were misdiagnosed)

**False Negatives**: 1 (Only one case of cancer was missed)
