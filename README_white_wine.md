# Predicting White Wine Quality from Physicochemical Properties

Regression and binary classification with Random Forest.

## Overview

This project uses the physicochemical properties of white wines (such as acidity, sugar, sulfur dioxide, density and alcohol) to predict their quality score. The quality is predicted in two ways:

1. **Regression:** predict the quality score itself.
2. **Binary classification:** predict whether a wine is "good" (quality >= 6) or not.

## Dataset

- **Source:** [Wine Quality dataset, UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/186/wine+quality) (white wine file: `winequality-white.csv`, values separated by `;`)
- **Size:** 4,898 white wine samples, 12 columns (11 features + `quality`); [X] rows remain after removing [X] duplicates
- **Features:** fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, alcohol
- **Target:** `quality`, a score from 3 to 9 given by tasters

## Workflow

1. **Data inspection:** shape, data types, missing values, duplicates and summary statistics.
2. **Data cleaning:** removed duplicate rows.
3. **Exploratory data analysis (EDA):** target distribution, feature distributions, outlier analysis (max/Q3 ratio and IQR), and correlation analysis.
4. **Modeling:** Random Forest as the baseline model. It was chosen because it does not require feature scaling and is robust to outliers and skewed features.
5. **Evaluation:** 5-fold cross-validation for both tasks, plus a confusion matrix for classification.
6. **Feature engineering:** new features were tested and compared with the original features using the same cross-validation.

Binary classification is used because the extreme quality scores have very few samples, which a multiclass model can barely learn after the data is split into folds.

## Key Findings

- Quality scores are concentrated around the middle values (mostly 5, 6 and 7), so the target is imbalanced.
- [Add 2-3 findings from your EDA, e.g., the features most correlated with quality and which features contain many outliers.]
- [Add the result of your feature engineering, e.g., whether the new features improved performance.]

## Model Results

5-fold cross-validation with Random Forest:

| Task | Metric | Score |
|---|---|---|
| Regression | R² | [X] |
| Regression | MAE | [X] |
| Binary classification | Accuracy | [X] |
| Binary classification | Precision | [X] |
| Binary classification | Recall | [X] |
| Binary classification | F1 | [X] |

- [Add one sentence interpreting the results, e.g., R² shows how much of the variance in quality the features explain, and MAE shows the average error in quality points.]
- Quality is a subjective sensory score, so physicochemical features alone cannot fully explain it.

## Limitations and Next Steps

- Results come from one dataset and are based on physicochemical features only (no information on grape variety, brand or vintage).
- Hyperparameters were not tuned.
- Next steps: hyperparameter tuning, comparing other models (e.g., gradient boosting), and combining with the red wine dataset.

## Repository Structure

```
.
├── white_wine_quality.ipynb     # full analysis
├── winequality-white.csv        # dataset (download from UCI)
└── README.md
```

## How to Run

```bash
pip install pandas numpy seaborn matplotlib scikit-learn jupyter
jupyter notebook white_wine_quality.ipynb
```

Place the CSV file in the same folder as the notebook. Because the file uses `;` as the separator, load it with `pd.read_csv('winequality-white.csv', sep=';')`.

## Tools

Python, pandas, NumPy, scikit-learn, Matplotlib, Seaborn

## Author

Rini Ramadhan Naim - [LinkedIn](https://www.linkedin.com/in/rini-ramadhan-naim-1b0286429)
