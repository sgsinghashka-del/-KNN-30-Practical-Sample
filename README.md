<div align="center">

# KNN / 30 Practical Samples

### A dark, portfolio-grade machine learning notebook for learning classification through real-world-inspired mini-projects.

[![Open Notebook](https://img.shields.io/badge/Open_Notebook-FF6F00?style=for-the-badge&logo=jupyter&logoColor=white)](KNN_30_Practical_Sample_IPYNB.ipynb)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![scikit--learn](https://img.shields.io/badge/scikit--learn-KNN-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Notebook](https://img.shields.io/badge/Format-Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Landing Page](https://img.shields.io/badge/Portfolio-Landing_Page-8B5CF6?style=for-the-badge&logo=html5&logoColor=white)](docs/index.html)

</div>

> **Portfolio note:** This is an educational KNN collection built around small, synthetic CSV datasets. It is excellent for learning the end-to-end workflow, but its perfect-looking scores should not be interpreted as production model performance.

<div align="center">

**9 use cases** · **1 notebook** · **KNN classification** · **interactive predictions** · **visual outputs**

</div>

---

## Executive summary

This repository presents a compact machine-learning portfolio project centered on **K-Nearest Neighbors (KNN)**. The notebook trains small classifiers, evaluates them, accepts custom user input, and renders a plot for each scenario.

The strongest learning value is not the individual accuracy score—it is the repeated, recognizable pipeline:

```text
CSV data → feature selection → train/test split → optional scaling
        → KNN(k=3) → evaluation → interactive prediction → visualization
```

The project includes examples from people analytics, education, finance, healthcare, security, customer analytics, email filtering, and recommendations.

## Explore the project

| Resource | Purpose |
|---|---|
| [Interactive notebook](KNN_30_Practical_Sample_IPYNB.ipynb) | Run and inspect all nine KNN examples |
| [HTML/CSS portfolio landing page](docs/index.html) | View the project as a darker AI/ML showcase |
| [Repository](https://github.com/sgsinghashka-del/-KNN-30-Practical-Sample) | Browse the complete source |

## What is inside?

| # | Mini-project | Input features | Output |
|---:|---|---|---|
| 01 | Salary category | Experience, Salary | Low / Medium / High |
| 02 | Employee promotion | Experience, Performance | Yes / No |
| 03 | Student result | Study hours, Attendance | Pass / Fail |
| 04 | Loan approval | Income, Credit score | Yes / No |
| 05 | Credit-card fraud | Amount, Time | Yes / No |
| 06 | Medical diagnosis | Sugar, BP | Yes / No |
| 07 | Customer churn | Years, Usage | Yes / No |
| 08 | Email spam | Number of links | Yes / No |
| 09 | Movie recommendation | Rating | Recommend / Not recommend |

## Technical anatomy

### Model

Most examples use:

```python
from sklearn.neighbors import KNeighborsClassifier

model = KNeighborsClassifier(n_neighbors=3)
model.fit(X_train, y_train)
prediction = model.predict(X_test)
```

### Evaluation

The notebook demonstrates several evaluation levels:

- `accuracy_score` for quick model checks
- `classification_report` for precision, recall, and F1-score
- `confusion_matrix` for class-level error inspection
- `predict_proba` in the employee-promotion example
- interactive predictions from keyboard input
- Matplotlib charts for visual interpretation

### Scaling insight

Scaling is used in the examples where feature magnitudes differ substantially, such as income versus credit score or transaction amount versus time. This matters because KNN is distance-based: an unscaled large-number feature can dominate the neighborhood calculation.

## Portfolio critique and engineering observations

### Strengths

- Clear beginner-friendly progression from data loading to prediction.
- Repeated structure makes the KNN workflow easy to compare across domains.
- Interactive inputs make every example feel tangible.
- The notebook combines metrics, predictions, and visualizations.
- The examples are small enough to run quickly in Colab or local Jupyter.

### Current limitations

- The repository currently contains the notebook but not the CSV files referenced by it (`salary.csv`, `promotion.csv`, `student.csv`, and others). Add those datasets beside the notebook before running it locally.
- Several examples use very small datasets and can report `1.0` accuracy with only a few test rows.
- Some prediction calls pass raw lists to estimators fitted with DataFrame feature names, which produces scikit-learn feature-name warnings.
- Most examples use a fixed `k=3` without comparing alternative values.
- Some examples do not use stratification, feature scaling, or a full classification report consistently.
- The medical, loan, fraud, and employment examples are demonstrations—not decision systems.

## Recommended next iteration

To turn this learning notebook into a stronger portfolio project:

1. Add the nine CSV datasets with a documented schema and data dictionary.
2. Replace list-based prediction inputs with DataFrames using the original feature names.
3. Add a reusable training function or scikit-learn `Pipeline`.
4. Compare `k` values with cross-validation and plot validation accuracy.
5. Add precision, recall, F1, and confusion matrices to every classifier.
6. Track class balance and test a stratified split consistently.
7. Add a `requirements.txt` and a reproducible environment file.
8. Separate notebook demonstrations from production-style Python modules.
9. Add responsible-AI notes for healthcare, credit, fraud, and employment scenarios.

## Run locally

### 1. Clone

```bash
git clone https://github.com/sgsinghashka-del/-KNN-30-Practical-Sample.git
cd -KNN-30-Practical-Sample
```

### 2. Install dependencies

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
python -m pip install --upgrade pip
python -m pip install pandas matplotlib scikit-learn jupyter
```

### 3. Add the referenced datasets

Place the CSV files expected by the notebook in the repository root:

```text
salary.csv
promotion.csv
student.csv
loan.csv
fraud.csv
diabetes.csv
churn.csv
spam.csv
movies.csv
```

### 4. Launch

```bash
jupyter notebook KNN_30_Practical_Sample_IPYNB.ipynb
```

You can also open the notebook directly in [Google Colab](https://colab.research.google.com/github/sgsinghashka-del/-KNN-30-Practical-Sample/blob/main/KNN_30_Practical_Sample_IPYNB.ipynb).

## Repository structure

```text
.
├── KNN_30_Practical_Sample_IPYNB.ipynb  # Main interactive notebook
├── docs/
│   ├── index.html                        # Dark AI/ML portfolio landing page
│   └── styles.css                        # Responsive visual system
├── assets/                               # Earlier lightweight visual assets
└── README.md
```

## Visual experience

The repository includes a dedicated HTML/CSS landing page with:

- dark hacker/tech visual language
- neon cyan, violet, and green accents
- responsive cards for all nine use cases
- pipeline visualization without external frameworks
- metric cards and model facts
- direct notebook and repository calls to action

Open it locally with:

```bash
python -m http.server 8000 --directory docs
```

Then visit <http://localhost:8000>.

For GitHub Pages, configure **Settings → Pages → Deploy from a branch → `main` → `/docs`**.

## Learning outcomes

After working through the notebook, you should understand:

- what supervised classification looks like in practice
- why feature scaling matters for distance-based algorithms
- how train/test splits influence evaluation
- how KNN uses neighboring observations to vote on a class
- how to collect an interactive prediction from a user
- why a perfect score on a toy dataset is not enough evidence of generalization



<div align="center">

**Built for learning. Styled for a portfolio. Evaluated with healthy skepticism.**

</div>
