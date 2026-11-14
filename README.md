# Credit Card Fraud Detection

I wanted to see how many false alarms a fraud model could avoid by raising its alert threshold. I picked the threshold on a validation set, then checked it once on a test set the model had never seen. Moving from 0.50 to 0.65 raised precision from **89% to 95%** while recall stayed at **80%**.

| Threshold | Frauds caught (of 99) | Frauds missed | False alarms |
|-----------|-----------------------|---------------|--------------|
| 0.50      | 79                    | 20            | 10           |
| 0.65      | 79                    | 20            | 4            |

On this test set the stricter threshold removed six false alarms without missing any extra fraud. On the validation set the same move cost one caught fraud, so I wouldn't expect it to be free every time.

## Data and model

I used the [Kaggle Credit Card Fraud Detection dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud), which contains 284,807 transactions from European cardholders in September 2013. Only 492 transactions (0.17%) were labeled as fraud.

I split the data 60/20/20 into training, validation and test sets, stratified so each one keeps the same fraud rate. I used `StandardScaler` for scaling, SMOTE to oversample the fraud class in the training data only, and a scikit-learn random forest to classify transactions. A logistic regression trained on the same data works as a baseline.

The notebook uses `predict_proba()` to get a fraud score for each transaction. It compares thresholds from 0.50 to 0.90 on the validation set and keeps the most precise one that still catches at least 80% of the fraud there. The test set is only used at the end.

## What to keep in mind

- The test set has 99 frauds, so one transaction moves precision or recall by about a point. The notebook prints the actual counts next to the percentages.
- Accuracy is above 99% for any model on this data because fraud is so rare. I report PR-AUC instead: 0.84 for the random forest and 0.76 for logistic regression.
- The data is from two days in 2013 and the features are anonymized, so the results say more about the threshold tradeoff than about fraud today.

## Run the notebook

1. **Clone the repository:**
   ```bash
   git clone https://github.com/DavidFinTech/High_Precision_Credit_Card_Fraud_Detection_Model.git
   ```
2. **Navigate into the project directory:**
    ```bash
    cd High_Precision_Credit_Card_Fraud_Detection_Model
    ```
3. **Install the required dependencies:**
    ```bash
    python -m pip install -r requirements.txt
    ```
4. Open `Credit Card Fraud Project.ipynb` in Jupyter Notebook or PyCharm and run all cells.
