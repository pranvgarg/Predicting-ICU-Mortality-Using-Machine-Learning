# 🏥 Predicting ICU Mortality Using Machine Learning: A Global Perspective 🌍

---

## 📑 Table of Contents
- [📖 Overview](#-overview)
- [📊 Dataset](#-dataset)
- [🛠️ Methodology](#️-methodology)
  - [🧹 Preprocessing](#-preprocessing)
  - [🤖 Modeling](#-modeling)
  - [📏 Evaluation Metrics](#-evaluation-metrics)
- [🎯 Key Results](#-key-results)
- [✨ Contributions and Novel Characteristics](#-contributions-and-novel-characteristics)
- [🔮 Future Work](#-future-work)
- [📚 References](#-references)
- [🌐 Read More on Medium](#-read-more-on-medium)

---

## 📖 Overview
Predicting in-hospital mortality in the ICU is a critical task that can significantly impact patient outcomes, resource allocation, and healthcare quality. This project leverages the **Global Open Source Severity of Illness Score (GOSSIS)** dataset to develop machine learning models aimed at predicting ICU mortality across diverse healthcare settings.

### 🎯 **Project Goal**
- **Primary**: Build a robust machine learning model to accurately predict ICU mortality.
- **Secondary**: Create a globally generalizable severity scoring system that outperforms traditional models like APACHE.

---

## 📊 Dataset
### 🌐 **Source**
The dataset originates from the **GOSSIS Consortium**, encompassing ICU data from:
- **Argentina**, **Australia**, **New Zealand**, **Bangladesh**, **India**, **Nepal**, **Sri Lanka**, **Brazil**, and the **United States**.

**💾 Public Subset**: Available on [Kaggle](https://www.kaggle.com/datasets/mitishaagarwal/patient/data) (91,713 rows).

### 🏷️ **Key Features**
- **Demographics**: Age, BMI, gender, ethnicity.
- **ICU Details**: Admission source, ICU type, pre-ICU stay duration.
- **Clinical Scores**: APACHE II & IIIj, Glasgow Coma Scale (GCS).
- **Vital Signs**: Heart rate, blood pressure, respiratory rate, temperature.
- **Chronic Conditions**: Diabetes, cirrhosis, leukemia, etc.
- **Outcome Variable**: ICU mortality (death during ICU stay).

### ⚠️ **Challenges**
- **Imbalanced Data**: ~80,000 survived vs ~7,000 passed away.
- **Missing Values**: Addressed via imputation and feature engineering.

---

## 🛠️ Methodology

### 🧹 **Preprocessing**
- **Data Cleaning**: Removed unnecessary columns and rows with missing values.
- **Feature Engineering**:
  - Summed comorbidities and GCS into total scores.
  - Applied **PCA** to reduce dimensionality from 83 to 44 features.
  - Encoded categorical variables using label encoding.
- **Class Imbalance**: Addressed using:
  1. Do Nothing 🙅‍♂️
  2. SMOTENC 🔄
  3. Class Weight Adjustment ⚖️

### 🤖 **Modeling**
We trained **27 models** using:
- **Algorithms**: Logistic Regression, Random Forest, XGBoost, MLP Neural Network, and more.
- **Strategies**: Class imbalance methods (above) applied to all models.

### 📏 **Evaluation Metrics**
Key metrics included:
- **Accuracy** ✅
- **Precision** 🎯
- **Recall** 🔍 (minimizing false negatives)
- **F1-Score** 🤝
- **ROC AUC** 📈
- **PR AUC** 📉

---

## 🎯 Key Results

### 🏆 **Best Model**: Multi-Layer Perceptron (MLP) with SMOTENC
- **Accuracy**: 92.71%  
- **Recall**: 90.18%  
- **Precision**: 94.57%  
- **F1-Score**: 92.32%  
- **ROC AUC**: 0.985  
- **PR AUC**: 0.9837  

### 📊 Comparison with APACHE
| Metric        | MLP with SMOTENC | APACHE |
|---------------|------------------|--------|
| **Accuracy**  | 0.86             | 0.90   |
| **Precision** | 0.31             | 0.44   |
| **Recall**    | 0.58             | 0.41   |
| **ROC AUC**   | 0.8430           | 0.8457 |

---

## ✨ Contributions and Novel Characteristics
- 🌍 **Diverse Dataset**: Integrated data from multiple countries and healthcare systems.
- ⚖️ **Balanced Data**: Applied **SMOTENC** to address class imbalance.
- 🤝 **Model Validation**: Compared machine learning models with traditional APACHE scores.
- 📖 **PubMed Analysis**: Validated feature importance using scientific literature.

---

## 🔮 Future Work
- 🌟 Explore **feature interactions** for improved interpretability.
- 🛠️ Use **Optuna** or similar tools for hyperparameter tuning.
- 🤝 Conduct **fairness assessments** to ensure unbiased predictions.
- ⏳ Incorporate **real-time ICU data** for dynamic predictions.

---

## 📚 References
1. [GOSSIS Dataset](https://gossis.mit.edu/)
2. [Patient Data on Kaggle](https://www.kaggle.com/datasets/mitishaagarwal/patient/data)
3. [PubMed API](https://pubmed.ncbi.nlm.nih.gov/)
4. [CDC: Trends in Inpatient Hospital Deaths](https://www.cdc.gov/nchs/products/databriefs/db118.htm)

---

## 🌐 Read More on Medium
For an in-depth explanation of the project, visit our Medium article:  
**[Predicting ICU Mortality Using Machine Learning: A Global Perspective](https://medium.com/@pg.garg.pranav/predicting-icu-mortality-using-machine-learning-a-global-perspective-dc18d009afb0)**