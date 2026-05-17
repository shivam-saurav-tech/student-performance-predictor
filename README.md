# Student Performance Predictor

A machine learning project that predicts whether a student will
pass or fail their final exam using behavioral and demographic
data — without relying on interim grades.

---

## Problem Statement

Schools lack early warning systems to identify at-risk students
before final exams. This project builds a predictive model using
only pre-exam behavioral data (study habits, absences, family
background) to flag students who need intervention early.

---

## Dataset

- **Source** : UCI Machine Learning Repository
- **Link**   : https://archive.ics.uci.edu/dataset/320/student+performance
- **Size**   : 395 students, 33 features (Math course)
- **Target** : Pass (G3 ≥ 10) or Fail (G3 < 10)

> Note: Interim grades G1 and G2 were intentionally excluded
> to simulate a real early-warning scenario where only
> behavioral data is available before exams.

---

## Project Structure

student-performance-predictor/
├── data/
│   └── student-mat.csv
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_preprocessing.ipynb
│   └── 03_model.ipynb
├── outputs/
│   └── figures/
│       ├── grade_distribution.png
│       ├── feature_analysis.png
│       ├── correlation_heatmap.png
│       ├── confusion_matrix.png
│       ├── feature_importance.png
│       ├── top3_features.png
│       └── parent_education.png
├── .gitignore
├── requirements.txt
└── README.md
---

## Approach

| Step | Description |
|------|-------------|
| EDA | Grade distribution, correlation heatmap, feature analysis |
| Preprocessing | One-hot encoding, train/test split (80/20), StandardScaler |
| Modelling | Logistic Regression, Decision Tree, Random Forest |
| Evaluation | 5-fold cross validation, confusion matrix, F1 score |
| Insights | Feature importance, risk group analysis |

---

## Results

| Model | CV Accuracy | Test Accuracy | F1 Score |
|-------|-------------|---------------|----------|
| Logistic Regression | ~68% | 62.0% | 0.72 |
| Decision Tree | ~67% | 65.8% | 0.78 |
| **Random Forest** | **71.8%** | **69.6%** | **0.79** |

> Results are consistent with published benchmarks on this
> dataset without interim grade features (Cortez & Silva, 2008).

---

## Key Insights

1. **Past failures** is the strongest predictor (importance: 0.197)
   — students with 2+ failures pass at only 28.6%

2. **High risk vs Low risk gap** — students with high failures
   AND high absences pass at 28.6% vs 75.4% for low risk
   students — a 47 point gap

3. **Study time** shows clear dose-response — every increase
   in weekly study time raises pass rate meaningfully

4. **Parental education** positively correlates with outcomes
   — likely reflecting home academic support environment

---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/yourusername/student-performance-predictor.git
cd student-performance-predictor
```

**2. Create virtual environment**
```bash
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # Mac/Linux
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Download dataset**

Download from UCI repository and place
`student-mat.csv` inside the `data/` folder.

**5. Run notebooks in order**
01_eda.ipynb
02_preprocessing.ipynb
03_model.ipynb
---

## Technologies Used

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.x-blue)
![NumPy](https://img.shields.io/badge/NumPy-1.x-orange)
![Scikit--learn](https://img.shields.io/badge/Scikit--learn-1.x-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)

- **Python 3.10+**
- **Pandas** — data manipulation and EDA
- **NumPy** — numerical operations
- **Matplotlib / Seaborn** — data visualisation
- **Scikit-learn** — model training and evaluation
- **Joblib** — model serialisation

---

## Resume Highlight

> Built an end-to-end student performance prediction system
> using Python, Pandas, NumPy and Scikit-learn on UCI dataset
> (395 students). Performed EDA, feature engineering and trained
> Random Forest classifier achieving 71.8% cross-validated
> accuracy. Identified that high-risk students (2+ failures,
> high absences) pass at only 28.6% vs 75.4% for low-risk
> students — a 47 point gap enabling actionable early
> intervention flagging.

---

## Author

**Shivam Saurav**
- GitHub  : github.com/saurav307
- LinkedIn: https://www.linkedin.com/in/shivam-saurav-3062bb277//in/yourprofile
- Email   : dar.saurav@email.com