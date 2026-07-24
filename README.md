# 🏇 Horse Racing Top 3 Prediction using Machine Learning

## 📌 Project Overview

This project develops a machine learning framework to predict whether a horse will finish in the **Top 3** of a race. Four supervised learning algorithms were implemented and compared:

- Logistic Regression
- CatBoost
- XGBoost
- LightGBM

The project evaluates each model using multiple classification metrics and selects the best-performing algorithm based on predictive performance.

---

## 🎯 Objective

The objective of this project is to build a binary classification model capable of predicting whether a horse will finish in the **Top 3** using historical race information.

Target Variable:

- **1** → Horse finishes in the Top 3
- **0** → Horse finishes outside the Top 3

---

## 📂 Dataset

The dataset consists of historical horse racing records containing race-specific and horse-specific characteristics.

Examples of features include:

- Official Rating (OR)
- Weight Carried
- Draw Position
- Horse Age
- Race Month
- Race Day
- Race Year
- Race Class
- Horse Sex
- Age Band
- Distance
- Surface
- Going
- Number of runners

Several post-race variables that would introduce data leakage were removed before modelling.

---

## ⚙️ Data Preprocessing

The following preprocessing steps were performed:

- Removal of data leakage variables
- Removal of betting odds (SP)
- Missing value imputation
- Numerical feature scaling
- One-Hot Encoding of categorical variables
- Chronological 80/20 train-test split
- Class imbalance handling using `scale_pos_weight`

---

## 🤖 Machine Learning Models

The following algorithms were implemented:

### Logistic Regression

Used as the baseline linear classification model.

### CatBoost

Gradient boosting algorithm designed to efficiently handle categorical data.

### XGBoost

Extreme Gradient Boosting with regularisation and histogram-based tree construction.

### LightGBM

Light Gradient Boosting Machine using leaf-wise tree growth for efficient learning.

---

## 📊 Model Evaluation

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Precision-Recall AUC (PR-AUC)
- Confusion Matrix
- ROC Curve
- Precision-Recall Curve

---

## 📈 Final Results

| Model | Accuracy | Top 3 Precision | Top 3 Recall | Top 3 F1 | ROC-AUC | PR-AUC |
|--------|----------|----------------|--------------|----------|---------|---------|
| **LightGBM** | **0.6409** | **0.4279** | **0.5621** | **0.4859** | **0.6668** | **0.4818** |
| CatBoost | 0.6398 | 0.4268 | 0.5629 | 0.4855 | 0.6664 | 0.4812 |
| XGBoost | 0.6406 | 0.4273 | 0.5597 | 0.4846 | 0.6667 | 0.4815 |
| Logistic Regression | 0.7119 | 0.6300 | 0.1106 | 0.1881 | 0.6543 | 0.4624 |

---

## 🏆 Best Model

**LightGBM** was selected as the final predictive model because it achieved:

- Highest Top 3 F1-score
- Highest ROC-AUC
- Highest PR-AUC

Although CatBoost and XGBoost produced very similar performance, LightGBM consistently achieved the strongest overall predictive performance.

---

## 📌 Feature Importance

The most influential predictors identified by the final LightGBM model were:

- Official Rating (OR)
- Weight Carried
- Horse Number
- Number of Runners
- Horse Age
- Race Month
- Draw Position
- Race Day
- Race Year
- Horse Sex
- Race Class

These findings indicate that both horse-specific characteristics and race conditions contribute substantially to predicting Top 3 finishes.

---

## 🛠 Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- CatBoost
- XGBoost
- LightGBM

---

## 📁 Repository Structure

```
Horse-Racing-Prediction/
│
├── data/
│   └── raceform.csv
│
├── notebooks/
│   └── race_horse_final.ipynb
│
├── images/
│   ├── confusion_matrices/
│   ├── roc_curves/
│   ├── pr_curves/
│   └── feature_importance.png
│
├── README.md
└── requirements.txt
```

---

## 🚀 How to Run

1. Clone the repository

```bash
git clone https://github.com/yourusername/horse-racing-top3-prediction.git
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Open the Jupyter Notebook

```bash
jupyter notebook
```

4. Run all notebook cells in sequence.

---

## 📚 Future Improvements

Potential enhancements include:

- Hyperparameter optimisation using Optuna or Bayesian Optimisation
- Feature engineering using historical horse performance
- Time-series cross-validation
- Probability calibration
- Model explainability using SHAP values
- Deep learning approaches for sequential race data

---

## 👩‍💻 Author

**Ayush Rawat**

MSc Business Analytics

University of Greenwich

---

## 📄 License

This project is intended for academic and research purposes.
