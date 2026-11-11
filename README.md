# Credit Card Fraud Detection

I wanted to see how many false alarms a fraud model could avoid by raising its alert threshold. In the notebook, moving the threshold from 0.50 to 0.75 raised precision from **88% to 92%** and lowered recall from **83% to 82%**. A larger share of the alerts were actual fraud, but the model also missed a slightly larger share of fraudulent transactions.

<img width="548" height="257" alt="Screenshot 2026-10-10 at 12 57 41 AM" src="https://github.com/user-attachments/assets/4817cd43-83f5-43d4-addf-a4b2863c8dc7" />

## Data and model

I used the [Kaggle Credit Card Fraud Detection dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud), which contains 284,807 transactions from European cardholders in September 2013. Only 492 transactions (0.17%) were labeled as fraud.

I used `StandardScaler` for scaling, SMOTE to oversample the fraud class in the training data, and a scikit-learn random forest to classify transactions. The notebook uses `predict_proba()` to get a fraud score for each transaction, then compares the results at the two thresholds.

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
