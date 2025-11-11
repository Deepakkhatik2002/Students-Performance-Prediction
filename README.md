```markdown
# Students Performance and Difficulties Prediction

**Predict whether a student will pass the final exam using machine learning.**  
This project uses the [Student Performance Dataset](https://archive.ics.uci.edu/ml/datasets/Student+Performance) from UCI Machine Learning Repository to classify students as *pass* or *fail* based on demographic, social, and academic features.

<div align="center">
  <img src="https://blog.kinems.com/content/images/2018/04/Tracking_Headline.png" alt="Student Performance" width="600"/>
</div>

<br>

<p align="center">
  <a href="http://www.inpt.ac.ma/" target="_blank">
    <img src="http://www.inpt.ac.ma/sites/default/files/logo.png" alt="INPT Logo" width="150"/>
  </a>
</p>

<p align="center">
  <strong>INPT – Rabat, Morocco</strong>
</p>

---

## Project Contributors

| Name | GitHub |
|------|--------|
| [AL JADD Mohammed](https://github.com/mohammedAljadd) | [@mohammedAljadd](https://github.com/mohammedAljadd) |
| [BOUJIDA Hafssa](https://github.com/hafssaboujida) | [@hafssaboujida](https://github.com/hafssaboujida) |
| [EL NABAOUI Nouhaila](https://github.com/Elnabaouinouhaila) | [@Elnabaouinouhaila](https://github.com/Elnabaouinouhaila) |

**Project Advisor:**  
[Prof. Amina Radgui](https://www.linkedin.com/in/amina-radgui-88017424/)

---

## Introduction

Education is a cornerstone of societal progress. The COVID-19 pandemic severely impacted global education systems, leading to a decline in student performance. This project leverages **machine learning** to predict student success and identify key influencing factors, enabling timely interventions by educators and parents.

---

## Motivation

To improve educational outcomes, institutions need **data-driven insights**. By analyzing historical student records, we can:
- Predict exam success/failure
- Identify at-risk students early
- Recommend actionable interventions

As IT students, we apply **machine learning** to tackle this real-world challenge.

---

## Problem Statement

We aim to solve a **binary classification problem**:

> **Will a student pass the final exam?** (`yes` / `no`)

### Objectives:
1. **Predict** student outcome using demographic & behavioral features.
2. **Compare** Logistic Regression, KNN, and SVM classifiers.
3. **Identify** the most influential factors on performance.
4. **Select** the best model (highest accuracy, balanced precision/recall).

---

## Dataset

- **Source**: [UCI Student Performance Dataset](https://archive.ics.uci.edu/ml/datasets/Student+Performance)
- **Size**: 395 students (Portuguese secondary schools)
- **Target**: `passed` → `yes` (pass) / `no` (fail)
- **Features**: 32 (demographic, family, social, academic)

---

## Data Processing

### 1. **Categorical Encoding**
Map string labels to integers:
```python
df['Mjob'] = df['Mjob'].map({'teacher': 0, 'health': 1, 'services': 2, 'at_home': 3, 'other': 4})
```

### 2. **Feature Scaling** (for non-binary columns)
```python
col = (col - mean(col)) / std(col)   # Z-score normalization
```
> Binary columns (0/1) are **not scaled**.

---

## Data Visualization

We used `matplotlib` and `seaborn` to explore patterns:

| Visualization | Purpose |
|--------------|--------|
| **Distribution Histograms** | Show frequency of categories (e.g., internet access) |
| **Boxplots** | Compare performance across feature values |
| **Correlation Matrix** | Highlight features most correlated with `passed` |

---

## Model Evaluation Metrics

| Metric | Description |
|-------|-----------|
| **Confusion Matrix** | TP, FP, TN, FN |
| **F1 Score** | Harmonic mean of precision & recall |
| **ROC Curve** | TPR vs FPR at various thresholds |
| **ROC-AUC Score** | Area under ROC (1.0 = perfect) |

---

## Algorithms Implemented

### 1. **Logistic Regression**
- Simple, interpretable baseline.

### 2. **K-Nearest Neighbors (KNN)**
- Non-parametric, distance-based.
- Hyperparameter: `k` tuned via accuracy plot & grid search.

### 3. **Support Vector Machine (SVM)**
- Tested **Linear**, **Polynomial**, and **RBF (Gaussian)** kernels.
- Tuned parameters: `C`, `degree`, `gamma` using validation cost minimization.

---

## Results Summary

| Algorithm | Accuracy | F1 Score | ROC-AUC | Training Time |
|---------|----------|----------|---------|----------------|
| **SVM (Linear)** | **84.38%** | **0.82** | **0.80** | 11ms |
| SVM (RBF) | 82.81% | 0.77 | 0.74 | 3ms |
| SVM (Poly) | 78.13% | 0.74 | 0.73 | 7ms |
| KNN | ~80% | ~0.78 | ~0.76 | Varies |
| Logistic Regression | ~78% | ~0.75 | ~0.72 | Fast |

> **Winner: SVM with Linear Kernel**

---

## Feature Importance (SVM Linear)

After training the best model, we extracted **positive** and **negative** factors:

### Positive Impact (Helps Success)
- Parents' education
- Guardian (non-parent)
- Desire for higher education
- Study time
- Parents' job

### Negative Impact (Leads to Failure)
- Age
- Health
- Going out with friends
- Absences
- Past failures

> **Note**: Some factors (e.g., health, age) may be dataset-specific due to limited size (n=395).

---

## Recommendations

Based on model insights:

| Stakeholder | Advice |
|-----------|--------|
| **Students** | Study regularly, minimize absences, focus on goals |
| **Parents** | Support education, ensure internet access, help with homework |
| **Schools** | Monitor absences & failures, provide counseling, early warnings |

---

## Project Structure

```
.
├── README.md                 ← This file
├── code.ipynb                ← Full analysis (Jupyter Notebook)
├── student-data.csv          ← Dataset
├── plots/                    ← All generated plots
│   ├── KNN.plot/
│   ├── SVM.plot/
│   └── project.cover/
└── requirements.txt          ← (Optional) Python dependencies
```

---

## How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/mohammedAljadd/Students-performance-and-difficulties-prediction.git
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```
3. Open `code.ipynb` in Jupyter and run all cells.

---

## Conclusion

We successfully built a **predictive model** with **84% accuracy** using **SVM (Linear)**. Key factors influencing performance were identified, enabling **proactive interventions**.

This project demonstrates how **machine learning** can support education systems — especially in post-pandemic recovery.

---

<div align="center">

**Thank you for your attention!**

<img src="https://user-images.githubusercontent.com/74038190/212284100-3614347d-3f0f-4d39-9f0b-1534d90b7d2b.gif" width="400"/>

</div>

---

**NB**: Results are based on the provided dataset and may not generalize beyond the two Portuguese schools.
``` 

---

**Save this as `README.md` in your project root.**  
It is **professional, well-structured, and fully self-contained** with visuals, tables, and navigation.
