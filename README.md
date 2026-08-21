# 🫀 Heart Disease Prediction 

## 📌 Project Overview

This project focuses on predicting the presence of heart disease using machine learning classification algorithms.

The goal is to build and compare multiple machine learning models, tune their hyperparameters, evaluate their performance using multiple metrics, and select a suitable final model for heart disease risk screening.

> **Note:** This project is an academic machine learning prototype and should not be considered a clinically validated diagnostic system.

---

## 🎯 Objectives

- Understand and explore the heart disease dataset.
- Perform data cleaning and exploratory data analysis (EDA).
- Preprocess numerical and categorical features.
- Build multiple machine learning classification models.
- Compare model performance using different evaluation metrics.
- Perform hyperparameter tuning using `GridSearchCV`.
- Use Stratified K-Fold Cross-Validation.
- Select a final model based on overall performance.
- Analyze the final model using a confusion matrix and feature coefficients.
- Provide suggestions for hospital/healthcare decision support.

---

## 📊 Dataset

The dataset contains patient-related health and clinical features used for heart disease prediction.

Important features include:

- Age
- Sex
- Resting Blood Pressure
- Serum Cholesterol
- Chest Pain Type
- Maximum Heart Rate Achieved
- Exercise-Induced Angina
- Resting ECG Results
- ST Depression (`oldpeak`)
- Number of Major Vessels
- Thalassemia
- Fasting Blood Sugar
- Slope of Peak Exercise ST Segment

The target variable represents the presence/absence of heart disease.

---

## 🛠️ Technologies and Libraries

### Programming Language
- Python

### Development Environment
- Jupyter Notebook

### Libraries
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib

---

## 🔄 Project Workflow

```text
Dataset
   ↓
Data Understanding
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
Data Preprocessing
   ↓
Train-Test Split
   ↓
Baseline Model Training
   ↓
Model Evaluation
   ↓
Hyperparameter Tuning
   ↓
Cross-Validation
   ↓
Final Model Selection
   ↓
Final Evaluation
   ↓
Feature Interpretation
   ↓
Hospital Recommendations
```

---

## 🤖 Machine Learning Models

The following classification algorithms were evaluated:

1. Logistic Regression
2. K-Nearest Neighbors (KNN)
3. Decision Tree
4. Random Forest
5. Support Vector Machine (SVM)

---

## 📈 Baseline Model Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 86.11% | 78.95% | 93.75% | 85.71% | 94.69% |
| KNN | **88.89%** | **83.33%** | 93.75% | 88.24% | **95.94%** |
| Decision Tree | 72.22% | 68.75% | 68.75% | 68.75% | 71.88% |
| Random Forest | 83.33% | 75.00% | 93.75% | 83.33% | 90.94% |
| SVM | **88.89%** | 80.00% | **100.00%** | **88.89%** | 95.62% |

---

## ⚙️ Hyperparameter Tuning

`GridSearchCV` was used to tune the following models:

- Logistic Regression
- KNN
- SVM
- Random Forest

### Best Parameters

**Logistic Regression**
```text
C = 1
solver = liblinear
```

**KNN**
```text
n_neighbors = 15
weights = uniform
metric = manhattan
```

**SVM**
```text
C = 10
gamma = auto
kernel = rbf
```

**Random Forest**
```text
n_estimators = 100
max_depth = 5
min_samples_leaf = 1
min_samples_split = 2
```

---

## 📊 Cross-Validation Results

5-fold Stratified Cross-Validation was used to obtain a more reliable estimate of model performance.

| Model | CV Accuracy | CV Precision | CV Recall | CV F1 | CV ROC-AUC |
|---|---:|---:|---:|---:|---:|
| **Logistic Regression** | **81.31%** | 80.36% | **79.74%** | **79.45%** | 85.34% |
| KNN | 80.54% | **82.71%** | 71.92% | 76.51% | **88.35%** |
| SVM | 74.31% | 71.24% | 75.13% | 72.09% | 82.65% |
| Random Forest | 79.90% | 80.18% | 76.54% | 77.48% | 86.31% |

---

## 🏆 Final Model

### Logistic Regression

Logistic Regression was selected as the final production candidate based on its overall cross-validation performance, particularly its accuracy, recall and F1-score, along with its test-set performance and interpretability.

### Final Test Performance

| Metric | Score |
|---|---:|
| Accuracy | **86.11%** |
| Precision | **76.19%** |
| Recall | **100.00%** |
| F1 Score | **86.49%** |
| ROC-AUC | **93.75%** |

### Final Confusion Matrix

```text
[[15  5]
 [ 0 16]]
```

This represents:

- True Negative: 15
- False Positive: 5
- False Negative: 0
- True Positive: 16

The test set contained **0 false negatives**, resulting in **100% recall** on this test split.

---

## 🔍 Feature Coefficient Analysis

The final Logistic Regression model was interpreted using its coefficients.

Some of the strongest absolute coefficients were:

| Feature | Coefficient |
|---|---:|
| `thal_normal` | -1.052083 |
| `num_major_vessels_2` | 0.936008 |
| `num_major_vessels_3` | 0.923826 |
| `chest_pain_type_4` | 0.845096 |
| `sex_1` | 0.769729 |
| `num_major_vessels_1` | 0.632172 |
| `resting_ekg_results_2` | 0.607813 |
| `thal_reversible_defect` | 0.567260 |
| `exercise_induced_angina_1` | 0.446266 |
| `oldpeak_eq_st_depression` | 0.431330 |

These coefficients represent associations learned by the Logistic Regression model and should not be interpreted as medical causation.

---

## 🏥 Hospital Recommendations

The model can be considered as a decision-support prototype for early risk screening.

Potential applications include:

- Identifying patients who may require further clinical evaluation.
- Prioritizing higher-risk patients for additional assessment.
- Supporting healthcare professionals with data-driven risk screening.
- Monitoring model performance using recall, precision, F1-score and ROC-AUC.
- Supporting preventive health programs and follow-up.

A positive prediction should lead to appropriate clinical evaluation rather than being treated as a definitive diagnosis.

---

## ⚠️ Challenges Faced

Some important challenges during the project included:

- Handling numerical and categorical features.
- Encoding categorical variables.
- Scaling numerical features.
- Avoiding data leakage.
- Selecting an appropriate machine learning algorithm.
- Hyperparameter tuning.
- Evaluating performance on a relatively small dataset.
- Comparing multiple evaluation metrics.
- Understanding false positives and false negatives.
- Interpreting Logistic Regression coefficients.
- Selecting the final model based on multiple criteria.

### Techniques Used

- Exploratory Data Analysis
- One-Hot Encoding
- Feature Scaling
- Scikit-learn Pipeline
- Train-Test Split
- Multiple Classification Algorithms
- GridSearchCV
- Stratified K-Fold Cross-Validation
- Confusion Matrix
- ROC-AUC Analysis
- Logistic Regression Coefficient Analysis

---

## 📁 Project Structure

```text
Heart-Disease-Prediction/
│
├── Heart_Disease_Prediction.ipynb
├── heart_disease_final_model.pkl
├── Hospital_Suggestions.txt
├── Model_Comparison_Report.txt
├── Challenges_and_Techniques.txt
├── model_comparison_baseline.csv
├── README.md
└── Data/
    └── Heart_data.csv
    └── labels.csv
    └── values.csv
```


## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/DEVAM0711/Heart-Disease-Prediction.git
```

### 2. Open the project folder

```bash
cd Heart-Disease-Prediction
```

### 3. Install required libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib jupyter
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

### 5. Open the notebook

Open:

```text
Heart_Disease_Prediction.ipynb
```

Run the notebook cells from top to bottom.

---

## 💾 Saved Model

The final trained model can be saved using Joblib:

```python
import joblib

joblib.dump(
    final_model,
    "heart_disease_final_model.pkl"
)
```

The saved model can later be loaded using:

```python
model = joblib.load(
    "heart_disease_final_model.pkl"
)
```

---

## 🔮 Future Scope

Possible future improvements include:

- Training with a larger dataset.
- Testing on an independent external dataset.
- Additional feature engineering.
- Comparing additional algorithms.
- Probability/risk threshold analysis.
- Model calibration.
- Explainable AI techniques.
- Developing a web-based prediction interface.
- Continuous model monitoring.
- Further clinical validation before any real-world healthcare deployment.

---

## ⚠️ Disclaimer

This project is developed for **educational and machine learning purposes**.

The model is a prototype decision-support system and is **not a substitute for professional medical diagnosis, clinical judgment, or treatment**. The reported performance is based on the provided dataset and test split. Larger and independent clinical validation would be required before real-world deployment.

---


## ⭐ Project Highlights

- Multiple ML classification models compared.
- Hyperparameter tuning with GridSearchCV.
- Stratified K-Fold Cross-Validation.
- Final Logistic Regression model selected.
- **86.11% test accuracy**
- **100% test recall**
- **93.75% test ROC-AUC**
- Confusion matrix and feature coefficient analysis.
- Hospital decision-support recommendations.
- Complete project maintained in a Jupyter Notebook.

---

## 👨‍💻 Author

**Devam Jasani**

Data Science & AI/ML Enthusiast

---


### 👨‍💻Contributing 



* Contributions are welcome! If you have suggestions or improvements, please fork the repository and submit a pull request.

---

## ⭐ If you found this project useful, don't forget to star this repository!
