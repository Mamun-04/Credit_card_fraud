# Credit Card Fraud Detection with SQL + Machine Learning

## Dataset

- **Source**: [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud)
- **Size**: ~143MB
- **Columns**:
  - `Time`: Seconds since the first transaction
  - `V1` to `V28`: PCA-transformed features (confidential for privacy)
  - `Amount`: Transaction amount
  - `Class`: Target label (`1` = fraud, `0` = legitimate)

To simulate real-world scenarios, the dataset was:
1. Loaded into a SQLite database (`transactions.db`)
2. Queried using SQL to extract relevant features (`V27`, `V28`, `Amount`, and `Class`)
3. Converted into a DataFrame for machine learning

No missing values, the dataset was clean. 
From the predictions of XGBoost and RandomForest, XGBoost performed better in detecting rare fraud cases. Confusion matrices were also made to give comparisons about the two performances

The dataset was also heavily imbalanced therefore a typical classifier trained on this will mostly learn to predict 0 (non-fraud) to optimize accuracy, since fraud is so rare. This meant the systems were able only predict fraud coreectly roughly 86% of the time.


