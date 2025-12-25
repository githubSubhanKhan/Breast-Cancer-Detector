# 🩺 Breast Cancer Detector

A **Machine Learning–based Breast Cancer Detection system** built using **Logistic Regression** to classify tumors as **Benign** or **Malignant**.  
This project prioritizes **medical safety**, focusing on reducing **False Negatives (FN)**, which is critical in cancer diagnosis where missing a malignant case can be life-threatening.

---

## 🚀 Project Overview

Breast cancer diagnosis is a **high-stakes medical problem** where model decisions must be made carefully.  
In this project, instead of optimizing only for accuracy, special emphasis is placed on **recall**, ensuring that **malignant cases are not missed**.

---

## 📂 Dataset

- Dataset imported from **Kaggle** using:
  - `kagglehub`
  - `KaggleDatasetAdapter`
- Total samples: **569**
- Total features: **32**
- Target variable: **`diagnosis`**
  - Benign (B)
  - Malignant (M)

Dataset structure was analyzed using the `.info()` method to understand feature types and completeness.

---

## 🛠️ Technologies & Libraries Used

- **Python**
- **kagglehub**
- **KaggleDatasetAdapter**
- **pandas, numpy**
- **scikit-learn**
  - `LogisticRegression` – Classification model
  - `train_test_split` – Dataset splitting
  - `LabelEncoder` – Encoding non-numeric target variable
  - `accuracy_score`, `recall_score`, `confusion_matrix` – Model evaluation

---

## ⚙️ Methodology

1. Imported dataset from Kaggle using `kagglehub` and `KaggleDatasetAdapter`
2. Explored dataset using `.info()` to understand features and data types
3. Encoded the non-numeric target variable `diagnosis` using **LabelEncoder**
4. Split the dataset:
   - **75% Training**
   - **25% Testing**
5. Trained a **Logistic Regression** model
6. Evaluated the model using accuracy, recall, and confusion matrix
7. Identified **False Negatives (FN)** as the most critical error
8. Optimized the model using:
   - **Class weights**
   - **Custom probability threshold**

---

## 📊 Initial Model Performance

- **Accuracy:** `95.10%`
- **Recall:** `90.74%`

### Confusion Matrix


| Metric | Value |
|------|------|
| True Negatives (TN) | 87 |
| False Positives (FP) | 2 |
| False Negatives (FN) | 5 |
| True Positives (TP) | 49 |

### ⚠️ Medical Insight

In cancer diagnosis:
> ❌ **False Negatives are extremely dangerous**  
A malignant tumor classified as benign can delay treatment and risk lives.

---

## 🔧 Model Optimization (Medical Safety Focus)

To reduce **False Negatives**, the following steps were applied:

- Assigned **class weights**:
  - Malignant class treated as **5× more critical** than Benign
- Adjusted **decision threshold to 0.3**
- Allowed a controlled increase in **False Positives** to eliminate **False Negatives**

---

## 📈 Optimized Model Performance

- **Accuracy:** `81.12%`
- **Recall:** `100%`

### Confusion Matrix (Optimized)


| Metric | Value |
|------|------|
| True Negatives (TN) | 62 |
| False Positives (FP) | 27 |
| False Negatives (FN) | 0 |
| True Positives (TP) | 54 |

### ✅ Key Achievement

- **Zero False Negatives**
- All malignant cases were correctly detected
- Safer and more suitable for **medical applications**

---

## 🧠 Key Takeaway

This project demonstrates that:
- **Accuracy alone is not sufficient** in medical ML systems
- **Recall and error type analysis** are far more important
- Controlled false alarms are acceptable to **save lives**

---

## 🔮 Future Improvements

- Experiment with **Random Forest**, **SVM**, or **XGBoost**
- Apply **ROC-AUC optimization**
- Add feature importance visualization
- Deploy as a **clinical decision support tool**
- Use cross-validation for better generalization

---

## 📌 Conclusion

This Breast Cancer Detector is a **safety-focused machine learning model** designed for medical diagnosis.  
By prioritizing **recall over accuracy**, the model ensures **no malignant case is missed**, making it more reliable and responsible for healthcare use.

---

⚠️ *This project is for educational purposes and should not replace professional medical diagnosis.*


