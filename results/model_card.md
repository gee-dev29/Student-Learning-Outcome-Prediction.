# Model card: student pass outcome example

## Purpose

This is a beginner exercise in binary classification. It compares Logistic Regression with a Decision Tree Classifier to predict a simplified pass outcome. It is not designed for decisions about real students.

## Data

The notebook uses 320 reproducible, synthetic rows in `data/student_outcomes.csv`. Inputs are weekly study hours, attendance percentage, previous assessment score, and assignment completion percentage. The target is `outcome` (`1` = pass, `0` = needs support). No real student data was used.

## Evaluation

Both models use the same stratified 75/25 train/test split (`random_state=42`), with 80 rows in the test set. Logistic Regression reached 78.75% accuracy; the Decision Tree reached 68.75%.

With rows as actual labels and columns as predictions (needs support, pass):

| Model | Needs support | Pass |
|---|---:|---:|
| Logistic Regression: actual needs support | 20 | 9 |
| Logistic Regression: actual pass | 8 | 43 |
| Decision Tree: actual needs support | 19 | 10 |
| Decision Tree: actual pass | 15 | 36 |

On this split, Logistic Regression made fewer errors of both kinds. The test results are small-sample teaching examples, not evidence of real-world performance.

## Limitations and cautions

- The data was generated for this exercise; real student outcomes are more complex.
- The features and target are based on simple assumptions and may encode unrealistic relationships.
- The dataset does not represent demographic, school, or other contextual differences.
- Accuracy does not show which kinds of mistakes were made; review both types of confusion-matrix errors.
- Neither model has been validated for fairness, reliability, or use outside this notebook.
- Do not use either model to label students, decide access to support, or make educational decisions.
