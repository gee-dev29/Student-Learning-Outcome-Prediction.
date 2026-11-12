# Student outcome prediction

This small project compares two classifiers on a made-up student dataset. The goal is to practise a complete classification workflow, not to assess real students.

## What is included

- [`student_outcome_prediction.ipynb`](./student_outcome_prediction.ipynb): walkthrough, training, evaluation, and model card
- [`data/student_outcomes.csv`](./data/student_outcomes.csv): synthetic dataset used in the notebook
- [`results/model_metrics.csv`](./results/model_metrics.csv): accuracy for both models
- [`results/confusion_matrices.csv`](./results/confusion_matrices.csv): counts for each actual/predicted class pair
- [`results/model_comparison.md`](./results/model_comparison.md): brief comparison and error notes
- [`results/model_card.md`](./results/model_card.md): purpose, data, results, and limitations

## Test-set snapshot

| Model | Accuracy |
|---|---:|
| Logistic Regression | 78.75% |
| Decision Tree | 68.75% |

Logistic Regression made fewer mistakes on this split. Its confusion matrix still shows 9 cases where someone who needed support was predicted to pass; accuracy alone would not reveal that error type. The notebook and model comparison file include the full matrices and both error counts.

## Run it

Use Python 3.10 or later. From this folder, install the packages and start Jupyter:

```bash
python -m pip install -r requirements.txt
jupyter notebook
```

Open `student_outcome_prediction.ipynb` and run the cells from top to bottom. The notebook uses the same stratified 75/25 train/test split for both models (`random_state=42`).

## Target and features

The target is `outcome`: `1` means pass and `0` means needs support. The four input features are weekly study hours, attendance percentage, previous assessment score, and assignment completion percentage. The CSV is generated from a fixed random seed, so it is reproducible.

## Important

The data is entirely synthetic. It contains no real student records and cannot show whether either model would work in a real school. Do not use these results to label, rank, or make decisions about students.
