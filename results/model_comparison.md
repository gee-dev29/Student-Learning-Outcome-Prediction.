# Model comparison

Both models were tested on the same 80 rows from one stratified split.

| Model | Accuracy |
|---|---:|
| Logistic Regression | 78.75% |
| Decision Tree | 68.75% |

The confusion matrices use rows for actual labels and columns for predictions, in the order needs support, pass:

| Model | Actual needs support: predicted support / pass | Actual pass: predicted support / pass |
|---|---:|---:|
| Logistic Regression | 20 / 9 | 8 / 43 |
| Decision Tree | 19 / 10 | 15 / 36 |

Logistic Regression performed better on this split: it got more cases right and made fewer of both kinds of errors. The tree more often predicted “needs support” for someone who actually passed (15 vs. 8). Both models also predicted “pass” for some students who needed support (9 and 10, respectively). Accuracy summarizes total correct predictions, so it hides which error happened; the confusion matrix makes that visible.

These are results on a small synthetic dataset; they do not establish which model would be better for real students. Run the notebook to recalculate results and refresh the CSV files.
