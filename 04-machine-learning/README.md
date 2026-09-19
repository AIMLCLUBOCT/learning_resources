# Module 04: Classical Machine Learning

> Master the core predictive algorithms of supervised and unsupervised learning using scikit-learn.

---

## 📋 Prerequisites
- Module 01 (Python & NumPy).
- Module 02 (Linear Algebra, Calculus, Statistics).
- Module 03 (Pandas & EDA).

---

## 🧠 Core Concepts

```
                            ┌───────────────────────────────┐
                            │       Machine Learning        │
                            └───────┬───────────────┬───────┘
                                    │               │
                    ┌───────────────▼┐             ┌▼───────────────┐
                    │   Supervised   │             │  Unsupervised  │
                    └───────┬────────┘             └────────┬───────┘
                            │                               │
            ┌───────────────┴───────────────┐       ┌───────┴───────┐
            ▼                               ▼       ▼               ▼
      Regression                      Classification Clustering  Dim. Reduction
    (Linear, Ridge, Lasso)        (Logistic, Trees, (K-Means,       (PCA,
                                    Forests, SVM)     DBSCAN)       t-SNE)
```

### 1. Supervised Learning: Regression
- Formulating continuous prediction ($y \in \mathbb{R}$).
- Ordinary Least Squares (OLS) Linear Regression.
- Loss function: Mean Squared Error (MSE), Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), $R^2$ score.
- Regularization: Ridge ($L_2$) and Lasso ($L_1$) to prevent overfitting.

### 2. Supervised Learning: Classification
- Binary vs. Multi-class prediction ($y \in \{0, 1\}$ or $\{0, 1, \dots, K\}$).
- Logistic Regression and the Sigmoid function: $\sigma(z) = \frac{1}{1 + e^{-z}}$.
- Support Vector Machines (SVMs), hyperplanes, support vectors, kernel trick (RBF kernel).
- Decision Trees: Information Gain, Entropy, Gini Impurity.
- Ensemble Methods:
  - Bagging: Random Forests (reducing variance).
  - Boosting: Gradient Boosting, XGBoost, LightGBM (reducing bias).

### 3. Unsupervised Learning
- **Clustering:** K-Means (centroid updates, elbow method), DBSCAN (density-based).
- **Dimensionality Reduction:** Principal Component Analysis (PCA), explained variance ratio.

### 4. Rigorous Model Evaluation
- Train / Validation / Test split.
- Stratified K-Fold Cross Validation.
- Classification Metrics: Accuracy, Precision, Recall, F1-Score, Confusion Matrix, ROC-AUC Curve.
- Hyperparameter Tuning: `GridSearchCV` and `RandomizedSearchCV`.

---

## 🗺️ Recommended Sequence

1. Study the [Scikit-Learn Getting Started Guide](https://scikit-learn.org/stable/getting_started.html).
2. Read the [Scikit-Learn Supervised Learning User Guide](https://scikit-learn.org/stable/supervised_learning.html).
3. Follow the [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course).
4. Build and tune an end-to-end model pipeline using `sklearn.pipeline.Pipeline`.

---

## 💻 Practical Exercises

### Exercise: Complete Scikit-Learn Pipeline
```python
from sklearn.datasets import load_breast_cancer
from sklearn.model_selection import train_test_split, cross_val_score
from sklearn.preprocessing import StandardScaler
from sklearn.ensemble import RandomForestClassifier
from sklearn.pipeline import Pipeline
from sklearn.metrics import classification_report

# 1. Load data
X, y = load_breast_cancer(return_X_y=True)

# 2. Train-test split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

# 3. Create reproducible Pipeline
pipeline = Pipeline([
    ('scaler', StandardScaler()),
    ('classifier', RandomForestClassifier(n_estimators=100, random_state=42))
])

# 4. Fit & Evaluate
pipeline.fit(X_train, y_train)
y_pred = pipeline.predict(X_test)

print("Classification Report:\n")
print(classification_report(y_test, y_pred))
```

---

## 💡 Project Ideas
- **Credit Card Fraud Detection:** Handle imbalanced tabular data using SMOTE/undersampling and optimize for Recall and ROC-AUC.
- **House Price Prediction Engine:** Multi-variable regression pipeline predicting real estate pricing with Ridge/Lasso regularization and XGBoost.

---

## 📖 Official Documentation & Resources
- 📖 [Scikit-Learn Official User Guide](https://scikit-learn.org/stable/user_guide.html)
- 🎓 [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course)
- 🎓 [DeepLearning.AI Machine Learning Specialization](https://www.deeplearning.ai/courses/machine-learning-specialization/)
