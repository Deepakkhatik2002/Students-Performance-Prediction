# Students Performance and Difficulties Prediction  
![Project Banner](https://blog.kinems.com/content/images/2018/04/Tracking_Headline.png)

**An academic machine learning project to predict student final exam success using classification algorithms.**

[![GitHub](https://img.shields.io/badge/GitHub-Repo-blue?logo=github)](https://github.com/Deepakkhatik2002/Students-Performance-Prediction)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-1.5-green)
![Scikit--Learn](https://img.shields.io/badge/ScikitLearn-1.2-orange)

---



---

## Contributors
- **[DEEPAK KHATIK](https://github.com/Deepakkhatik2002)**
  
---

## Project Overview

This project uses **machine learning** to predict whether a student will **pass or fail** the final exam based on demographic, social, and academic features. We compare three classification algorithms:

| Algorithm | Accuracy | F1-Score | ROC AUC |
|---------|----------|---------|--------|
| **SVM (Linear Kernel)** | **84.38%** | **0.82** | **0.80** |
| KNN | 78–82% | 0.74–0.77 | 0.73–0.74 |
| Logistic Regression | ~80% | ~0.78 | ~0.76 |

> **Winner: Support Vector Machine (SVM) with Linear Kernel**

---

## Dataset

- **Source:** [UCI Machine Learning Repository – Student Performance](https://archive.ics.uci.edu/ml/datasets/Student+Performance)
- **Size:** 395 students (Portuguese secondary schools)
- **Features:** 30+ (demographics, family, study habits, absences, etc.)
- **Target:** `passed` → `yes` / `no`

---

## Key Objectives

1. **Predict exam success** using student data.
2. **Compare Logistic Regression, KNN, and SVM**.
3. **Identify factors** influencing academic performance.
4. **Provide actionable insights** for students, parents, and schools.

---

## Methodology

### 1. Data Preprocessing
```python
# Map categorical variables
df['Mjob'] = df['Mjob'].map({'teacher': 0, 'health': 1, 'services': 2, 'at_home': 3, 'other': 4})

# Feature scaling (except binary columns)
df[col] = (df[col] - df[col].mean()) / df[col].max()




```markdown
# Students Performance and Difficulties Prediction  
![Project Banner](https://blog.kinems.com/content/images/2018/04/Tracking_Headline.png)

**An academic machine learning project to predict student final exam success using classification algorithms.**


[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-1.5-green)
![Scikit--Learn](https://img.shields.io/badge/ScikitLearn-1.2-orange)

---



---

## Contributors
- **[DEEPAK](https://github.com/Deepakkhatik2002)**  

---

## Project Overview

This project uses **machine learning** to predict whether a student will **pass or fail** the final exam based on demographic, social, and academic features. We compare three classification algorithms:

| Algorithm | Accuracy | F1-Score | ROC AUC |
|---------|----------|---------|--------|
| **SVM (Linear Kernel)** | **84.38%** | **0.82** | **0.80** |
| KNN | 78–82% | 0.74–0.77 | 0.73–0.74 |
| Logistic Regression | ~80% | ~0.78 | ~0.76 |

> **Winner: Support Vector Machine (SVM) with Linear Kernel**

---

## Dataset

- **Source:** [UCI Machine Learning Repository – Student Performance](https://archive.ics.uci.edu/ml/datasets/Student+Performance)
- **Size:** 395 students (Portuguese secondary schools)
- **Features:** 30+ (demographics, family, study habits, absences, etc.)
- **Target:** `passed` → `yes` / `no`

---

## Key Objectives

1. **Predict exam success** using student data.
2. **Compare Logistic Regression, KNN, and SVM**.
3. **Identify factors** influencing academic performance.
4. **Provide actionable insights** for students, parents, and schools.

---

## Methodology

### 1. Data Preprocessing
```python
# Map categorical variables
df['Mjob'] = df['Mjob'].map({'teacher': 0, 'health': 1, 'services': 2, 'at_home': 3, 'other': 4})

# Feature scaling (except binary columns)
df[col] = (df[col] - df[col].mean()) / df[col].max()
```

### 2. Exploratory Data Analysis (EDA)
- Histograms of categorical features
- Boxplots of numerical vs. target
- Correlation heatmap

### 3. Model Training & Evaluation
| Metric | Purpose |
|-------|--------|
| **Confusion Matrix** | Visualize TP/TN/FP/FN |
| **F1-Score** | Balance precision & recall |
| **ROC Curve & AUC** | Model discrimination power |

---

## Results

### Best Model: **SVM (Linear Kernel)**
| Metric | Value |
|-------|-------|
| Training Time | 11ms |
| **Accuracy** | **84.38%** |
| **F1-Score** | **0.82** |
| **ROC AUC** | **0.80** |

![SVM ROC Curve](https://github.com/mohammedAljadd/Students-performance-and-difficulties-prediction/blob/main/plots/SVM.plot/rocLF.PNG)

---

## Feature Importance (Factor Analysis)

### Positive Factors (Help Success)
| Factor | Insight |
|------|--------|
| **Parents' Education** | Educated parents support learning |
| **Higher Education Goal** | Motivated students perform better |
| **Study Time** | More study → higher chance of passing |
| **Parents' Job Stability** | Financial support enables resources |
| **Guardian (Other)** | Non-parent guardians may offer structured support |

### Negative Factors (Risk of Failure)
| Factor | Insight |
|------|--------|
| **Absences** | Missed classes → poor preparation |
| **Failures** | Past failure predicts future risk |
| **Going Out** | Excessive socializing reduces study time |
| **Age** | Older students may face distractions |
| **Health** | (Context-specific; needs larger data) |

> **Note:** Some factors (e.g., Health, Age) are dataset-specific and may not generalize.

---

## Recommendations

| Stakeholder | Advice |
|-----------|--------|
| **Students** | Study regularly, minimize absences, set clear goals |
| **Parents** | Support education, provide study space, monitor attendance |
| **Schools** | Early intervention for at-risk students, parent alerts on absences |
| **Government** | Subsidize internet access and tutoring for low-income families |

---

## Project Structure
```
.
├── code.ipynb                  # Full analysis & implementation
├── student-data.csv            # Dataset
├── plots/
│   ├── KNN.plot/               # KNN results
│   ├── SVM.plot/               # SVM results
│   └── project.cover/          # Visuals & infographics
├── README.md                   # This file
└── requirements.txt
```

---

## How to Run

```bash
# Clone the repo
git clone -
cd Students-performance-and-difficulties-prediction

# Install dependencies
pip install -r requirements.txt

# Run Jupyter Notebook
jupyter notebook code.ipynb
```

---

## Requirements (`requirements.txt`)
```txt
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
```

---

## Conclusion

> **SVM with linear kernel** achieved **84.38% accuracy** in predicting student success.  
> Key success drivers: **study time, parental education, motivation**.  
> Risk factors: **absences, failures, excessive socializing**.

This model enables **early intervention** to reduce failure rates and improve educational outcomes.

---

<div style="text-align:center;">
    <h2>Thank You!</h2>
    <img src="https://i.imgur.com/7jQyWnA.png" width="300"/>
</div>

---

**"Education is the most powerful weapon which you can use to change the world."** – Nelson Mandela

---
``` 

---

**Save this as `README.md` in your project root.**  
This version is clean, professional, GitHub-friendly, and visually appealing.
