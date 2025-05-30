# 🩺 Breast Cancer Detection using Logistic Regression

## 🔍 Binary Classification with Logistic Regression

This project demonstrates how to build a binary classification model using **Logistic Regression** with **L1 regularization** on the **Breast Cancer Wisconsin Dataset**. The model classifies whether a tumor is **malignant** or **benign** based on various cellular features.

---

## 📌 Objective

To train a logistic regression model that:
- Identifies malignant vs benign tumors
- Selects important features automatically using **L1 regularization**
- Evaluates model performance with multiple metrics
- Tunes the decision threshold for optimal performance

---

## 🛠️ Tools & Libraries

- `Python 3`
- `Pandas`
- `NumPy`
- `Scikit-learn`
- `Matplotlib`

---

## 📊 Dataset

**Dataset Name:** Breast Cancer Wisconsin (Diagnostic)  
**Source:** [Kaggle Dataset Link](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)  
**Features:** 30 numerical features based on cell nucleus properties  
**Target:**  
- `1` → Malignant  
- `0` → Benign  

---

## 🧪 Methodology

1. **Data Loading & Preprocessing**
   - Loaded dataset using `pandas`.
   - Removed irrelevant columns (e.g., ID).
   - Split data into train/test sets (80/20 split).
   - Standardized features using `StandardScaler`.

2. **Modeling with Logistic Regression**
   - Trained **L1-regularized logistic regression** (`penalty='l1'`, `solver='liblinear'`).
   - Why L1? Because many features were **highly correlated** (correlation values reaching 1).  
     L1 regularization helps with **feature selection**, improving model generalizability.

3. **Evaluation Metrics**
   - **Confusion Matrix**
   - **Precision**
   - **Recall**
   - **F1 Score**
   - **ROC Curve and AUC Score**

4. **Threshold Tuning**
   - Tuned classification threshold across different metrics:
     | Metric        | Optimal Threshold |
     |---------------|-------------------|
     | F1 Score      | **0.46**          |
     | Precision     | **0.71**          |
     | Recall        | **0.00**          |
     | Accuracy      | **0.46**          |

   - Used `model.predict_proba` to get predicted probabilities.
   - Applied custom threshold to maximize each metric individually.

5. **Sigmoid Function Explained**

   Logistic Regression uses the sigmoid function to convert the linear combination of inputs into a probability:

   \[
   \sigma(z) = \frac{1}{1 + e^{-z}}
   \]

   - Output: a value between 0 and 1 representing the probability that the input belongs to the positive class (malignant).
   - This probability is then compared to a **threshold** to determine the final binary prediction.

---

## 📈 Results Summary

- Logistic Regression with **L1 regularization** performed well with clear feature reduction.
- **ROC-AUC** indicated good separability between malignant and benign cases.
- Threshold tuning allowed fine control over precision/recall trade-offs depending on clinical priorities.

---

