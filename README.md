### 🧠 **Anomaly Detection Model Based on the Titanic Dataset**

This project implements a classification-based anomaly detection approach using a synthetic Titanic dataset of **409,856 samples**. The goal is to identify anomalies (or non-survivors) based on passenger attributes using machine learning techniques.

---

### ⚙️ **Workflow Overview**

1. **Synthetic Data Generation**:
   - A Titanic-like dataset was created with random sampling for categorical features and normal/uniform distributions for continuous features.
   - Features include: `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare`, `Embarked`, and the binary target `Survived`.

2. **Preprocessing & Feature Engineering**:
   - Dropped non-informative columns (`PassengerId`, `Name`, `Ticket`, `Cabin`).
   - Missing values in `Age` and `Embarked` filled with median/mode.
   - Categorical variables `Sex` and `Embarked` were one-hot encoded.
   - A new feature `FamilySize` was engineered as `SibSp + Parch + 1`.
   - Features were standardized using `StandardScaler`.

3. **Model Selection & Training**:
   - The dataset was split into training and testing sets (80/20 stratified).
   - Multiple classical models were evaluated:
     - Logistic Regression
     - K-Nearest Neighbors
     - Decision Tree
     - XGBoost (final chosen model)
   - SVM and Random Forest were excluded due to high computational cost on large data.
   - The best-performing model, **XGBoost**, was selected based on accuracy and F1 score.

4. **Evaluation**:
   - Evaluation metrics included:
     - Accuracy
     - F1 Score
     - Confusion Matrix
     - Classification Report
   - XGBoost demonstrated strong performance and generalization capability.

5. **Prediction & Submission**:
   - The trained model was applied to the full test dataset (synthetic set of 409,856 rows).
   - Predictions were saved in `submission.csv` in the required format with headers: `id`, `anomaly`.

6. **Visualization & Insights**:
   - A correlation heatmap was plotted to visualize feature relationships.
   - Survival distribution was plotted using a count plot.

---

### ✅ **Final Deliverable**
- `submission.csv` contains 409,856 predictions with headers.
- The model is suitable for large-scale inference and anomaly classification.

---
