# High-Precision Credit Card Fraud Detection Model
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=flat&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=flat&logo=pandas&logoColor=white)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=flat&logo=jupyter&logoColor=white)

### Problem Statement
Banks and other financial institutions process millions of transactions every day, most of which are legitimate. In this dataset, fraudulent transactions account for only 0.17% of the total.

This imbalance in data can make it difficult for models to detect fraud while keeping false alarms low. These false alarms can block valid transactions, leading to client frustration, increased customer service costs, and lost revenue.

### Dataset & Class Imbalance
The dataset used is sourced from Kaggle's [Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud). 

It contains transactions made by European credit cardholders in September 2013. 

* **Total Transactions:** 284,807
* **Legitimate Transactions (Class 0):** 284,315 (99.83%)
* **Fraudulent Transactions (Class 1):** 492 (0.17%)

Therefore, I developed an end-to-end predictive machine learning pipeline in Python that balances a strong security system with a smooth user experience following this process.

### Strategic Process:

1. **Data Normalization**
Imported 'StandardScaler' to ensure excessive differences between metrics (like large dollar amounts and tiny variable decimals) held equal mathematical weight in training the model.

2. **Imbalance Mitigation**
Implemented SMOTE (Synthetic Minority Over-sampling Technique) to generate realistic artificial fraud examples to create a perfectly balanced training environment which forces the algorithm to learn the actual threat patterns instead of lazily just categorizing a transaction as normal because of its extended length in the database.

3. **Ensemble Learning**
Employed a ‘Random Forest Classifier’ 
to evaluate transactions using hundreds of decision trees, reducing that way the bias and instability associated with single-algorithm models.

### Business Result & Tradeoffs:
Delivered a high calibre fraud detection system optimized for precision (from 88% to 92%) that instead of relying on the 50%+ default threshold, requires a strong algorithmic consensus (75%+) to trigger a fraud alert. Consequently, the pipeline drastically reduces false positive warnings. Whereas the solution sacrifices a bit of recall, which went from 83% to 82%, it effectively captures malicious transfers while ensuring that legitimate customers experience reduced friction when making their day-to-day operations. The model displays its confidence percentage levels using predict_proba().`

<img width="548" height="257" alt="Screenshot 2026-10-10 at 12 57 41 AM" src="https://github.com/user-attachments/assets/4817cd43-83f5-43d4-addf-a4b2863c8dc7" />

### Tech Stack:
* **Language:** Python 3.8+
* **Data Manipulation & Analysis:** Pandas, NumPy
* **Machine Learning & Preprocessing:** Scikit-Learn (`StandardScaler`, `RandomForestClassifier`), Imbalanced-Learn (`SMOTE`)
* **Data Visualization:** Matplotlib, Seaborn

### Installation:
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
4. **Open Credit Card Fraud Project.ipynb in Jupyter Notebook or PyCharm and run all cells.**

