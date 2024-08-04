# mlops-zoomcamp
## Problem description:
### Objective:
Develop a machine learning model to predict customer churn for a financial services company. The model will help identify customers who are likely to leave the company, enabling targeted retention strategies.
### Background:
Kaggle Bank Customer Churn Dataset Customer churn is a critical issue for the company, as acquiring new customers is often more costly than retaining existing ones. By predicting which customers are likely to churn, the company can take proactive measures to prevent customer loss, thereby improving customer satisfaction and increasing overall profitability.
### Data Source and Description:
https://www.kaggle.com/datasets/gauravtopre/bank-customer-churn-dataset
The dataset consists of customer information, including demographic details, account status, and interaction history with the company. The key features include:
- customer_id: Unique identifier for each customer.
- credit_score: The credit score of the customer.
- country: Country of residence of the customer.
- gender: Gender of the customer.
- age: Age of the customer.
- tenure: Number of years the customer has been with the company.
- balance: Current balance in the customer's account.
- products_number: Number of products the customer is subscribed to.
- credit_card: Whether the customer owns a credit card.
- active_member: Whether the customer is actively engaged with the company.
- estimated_salary: Estimated annual salary of the customer.
- churn (Target): Whether the customer has churned (1 for yes, 0 for no).
### Goal:
Build and evaluate a classification model that accurately predicts the probability of a customer churning. The model’s predictions will be used to identify high-risk customers and inform retention strategies.

### Evaluation Metric:
The model will be evaluated based on accuracy, precision, recall, F1 score, and the Area Under the Receiver Operating Characteristic Curve (AUC-ROC) to balance the trade-off between false positives and false negatives.

### Experiment tracking and model registry:
#### MLfow
conda env list
conda activate finalproject
mlflow --version
python preprocess_data.py --raw_data_path .\data --dest_path ./output
mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root ./mlruns --host 127.0.0.1 --port 5000
python train.py --data_path ./output
python hpo.py
python register_model.py
#### Prefect
