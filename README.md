# Wine Quality Prediction Using Machine Learning

## 📌 Project Overview

This project leverages machine learning techniques to predict the quality of red and white Portuguese wines based on their physicochemical characteristics. Traditionally, wine quality has been assessed through subjective sensory evaluations by experts, but this project introduces a data-driven approach that enhances consistency, scalability, and efficiency.

The dataset used is publicly available and contains 6,497 wine samples, each with 11 numerical features and a quality rating from 3 to 9.

---

## 🧪 Dataset Information

- **Source**: UCI Machine Learning Repository
- **Samples**: 6,497
- **Features**: 
  - Fixed acidity
  - Volatile acidity
  - Citric acid
  - Residual sugar
  - Chlorides
  - Free sulfur dioxide
  - Total sulfur dioxide
  - Density
  - pH
  - Sulphates
  - Alcohol
- **Target**: Wine quality score (3–9), later transformed into binary labels:
  - `1` for good quality (score > 5)
  - `0` for not good quality (score ≤ 5)

---

## 🧹 Data Preprocessing

1. **Missing Value Treatment**: Imputed using column means.
2. **Data Type Conversion**: Converted non-numeric columns using `pd.to_numeric()`.
3. **Correlation Analysis**: Heatmap used to identify multicollinearity. Dropped highly correlated features like `total sulfur dioxide`.
4. **Label Encoding**: Converted wine type (white/red) to binary.
5. **Feature Scaling**: Normalized using `MinMaxScaler`.

---

## 🧠 Models Used

- **Logistic Regression**: A simple linear classifier for binary classification.
- **Support Vector Classifier (SVC)**: Non-linear classifier using RBF kernel.
- **XGBoost Classifier**: Gradient boosting method known for high performance on structured data.

---

## 🏋️‍♂️ Training and Evaluation

- **Data Split**: 80% training, 20% testing
- **Normalization**: All features scaled to [0, 1]
- **Metrics**:
  - ROC AUC Score
  - Accuracy
  - F1-Score
  - Confusion Matrix
  - Classification Report

### ✅ Model Performance

| Model               | Validation Accuracy | F1-Score |
|--------------------|---------------------|----------|
| Logistic Regression| 68.6%               | 0.68     |
| SVC                | 70.7%               | 0.71     |
| **XGBoost**        | **80.4%**           | **0.82** |

> **XGBoost** demonstrated the best balance between bias and variance, showing strong generalization and no signs of overfitting.

---

## 📊 Key Insights

- **Feature Impact**: Alcohol content had a strong correlation with wine quality.
- **Binary Classification**: Simplified the model's objective to assist real-world decisions like premium labeling.
- **Business Relevance**:
  - Reduces reliance on subjective testing
  - Cuts cost and improves consistency
  - Helps identify critical production factors
  - Enhances quality assurance in manufacturing pipelines

---

## 🔍 Future Work

- Hyperparameter tuning using GridSearchCV
- Cross-validation for robustness
- Feature importance analysis and further feature selection
- Integration with more diverse datasets
