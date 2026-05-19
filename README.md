# 🎓 Student Behavioral Risk Analytics & Burnout Prediction

An end-to-end predictive machine learning pipeline that analyzes the impact of Generative AI tools, academic habits, and psychological indicators on student burnout risk. This project evaluates multiple classification frameworks on a dataset of 50,000 student profiles to isolate key behavioral risk factors.

---

## 📊 Performance Summary Matrix

| Metric | LightGBM (Winner) | Random Forest | Logistic Regression |
| :--- | :--- | :--- | :--- |
| **Overall Accuracy** | **53.00%** | 52.30% | 51.97% |
| **Macro F1-Score** | **53.08%** | 51.04% | 51.74% |
| **High-Risk Precision** | **66.00%** | *Evaluated* | *Evaluated* |

> 📌 **Key Insight:** While predicting overall student trends is complex, the final **LightGBM Classifier achieves a sharp 66% Precision when flagging "High" Burnout Risk**, making it highly reliable for targeted early intervention systems.

---

## 🛠️ System Architecture & Workflow

### 1. Exploratory Data Analysis (EDA)
* Automated structural validation across 50,000 unique student behavior records.
* Outlier checking, verification of missing data boundaries, and target balance analysis.

### 2. Feature Engineering & Preprocessing
* **Categorical Encoding:** Leveraged `LabelEncoder` to cleanly transform text variables (`Major_Category`, `Year_of_Study`, `Primary_Use_Case`, etc.) into model-ready structural integers.
* **Feature Scaling:** Used `StandardScaler` to normalize numeric metrics like GPA, traditional study hours, and weekly GenAI usage distributions.
* **Leakage Prevention:** Explicitly dropped `Post_Semester_GPA` from the input features to eliminate target leakage and ensure real-world production validity.

### 3. Multi-Model Evaluation Loop
* Partitioned the dataset using a strict 80/20 stratified split (`X_train: 40,000`, `X_test: 10,000`) to preserve class balances.
* Trained and compared three distinct architectures side-by-side: a gradient-boosting tree structure (**LightGBM**), a bagging ensemble (**Random Forest**), and a linear baseline (**Logistic Regression**).
* Isolated final feature weights using tree split-count analysis to determine the primary drivers of academic exhaustion.

---

## 📁 Repository Structure

```text
├── student_burnout_risk_prediction.ipynb  # Core Google Colab Development Notebook
└── README.md                              # Professional System Documentation


# 🎓 Student Behavioral Risk Analytics & Burnout Prediction

An end-to-end predictive machine learning pipeline that analyzes the impact of Generative AI tools, academic habits, and psychological indicators on student burnout risk. This project evaluates multiple classification frameworks on a dataset of 50,000 student profiles to isolate key behavioral risk factors.

---

## 📊 Performance Summary Matrix

| Metric | LightGBM (Winner) | Random Forest | Logistic Regression |
| --- | --- | --- | --- |
| **Overall Accuracy** | **53.00%** | 52.30% | 51.97% |
| **Macro F1-Score** | **53.08%** | 51.04% | 51.74% |
| **High-Risk Precision** | **66.00%** | *Evaluated* | *Evaluated* |

> 📌 **Key Insight:** While predicting overall student trends is complex, the final **LightGBM Classifier achieves a sharp 66% Precision when flagging "High" Burnout Risk**, making it highly reliable for targeted early intervention systems.

---

## 🛠️ System Architecture & Workflow

### 1. Exploratory Data Analysis (EDA)

* Automated structural validation across 50,000 unique student behavior records.
* Outlier checking, verification of missing data boundaries, and target balance analysis.

### 2. Feature Engineering & Preprocessing

* **Categorical Encoding:** Leveraged LabelEncoder to cleanly transform text variables (Major_Category, Year_of_Study, Primary_Use_Case, etc.) into model-ready structural integers.
* **Feature Scaling:** Used StandardScaler to normalize numeric metrics like GPA, traditional study hours, and weekly GenAI usage distributions.
* **Leakage Prevention:** Explicitly dropped Post_Semester_GPA from the input features to eliminate target leakage and ensure real-world production validity.

### 3. Multi-Model Evaluation Loop

* Partitioned the dataset using a strict 80/20 stratified split (X_train: 40,000, X_test: 10,000) to preserve class balances.
* Trained and compared three distinct architectures side-by-side: a gradient-boosting tree structure (LightGBM), a bagging ensemble (Random Forest), and a linear baseline (Logistic Regression).
* Isolated final feature weights using tree split-count analysis to determine the primary drivers of academic exhaustion.

---

## 📁 Repository Structure

```text
├── student_burnout_risk_prediction.ipynb  # Core Google Colab Development Notebook
└── README.md                              # Professional System Documentation

```

---

## 🚀 Technical Requirements

To run the development notebook locally or in your own cloud environment, ensure you have the following dependencies installed:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn lightgbm

```

---

## 🎯 Strategic Core Insights

* **Target Isolation:** LightGBM handled the non-linear interactions between heavy GenAI usage and academic indicators with the lowest overall validation loss.
* **Feature Importance:** The final evaluation chart clearly identifies specific behavioral patterns—such as exam-related anxiety levels, total weekly GenAI hours, and traditional reading allocations—as the dominant predictive signals for student burnout.
