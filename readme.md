# Olist Customer Churn Prediction (PySpark)

This project builds an end-to-end **customer churn prediction pipeline** using the Olist e-commerce dataset. The goal is to identify customers who are likely to become inactive so that businesses can take proactive retention measures.

---

## **🔍 Project Overview**

The analysis integrates multiple Olist datasets—**customers**, **orders**, **order items**, **order payments**—and constructs customer-level features.
A **Logistic Regression model (PySpark MLlib)** is trained to classify whether a customer is *churned* or *active*.

---

## **📌 Dataset Details**

The following Olist datasets were used:

* `customers_dataset.csv`
* `orders_dataset.csv`
* `order_items_dataset.csv`
* `order_payments_dataset.csv`
* `final_customer_features.csv` (engineered features)

These were loaded and processed using **PySpark** and **Spark SQL**.

---

## **🛠️ Technologies Used**

| Component           | Technology                 |
| ------------------- | -------------------------- |
| Data Processing     | PySpark, Spark SQL         |
| Feature Engineering | Spark DataFrame, SQL Joins |
| Model Building      | PySpark MLlib              |
| Visualization       | Matplotlib                 |
| Language            | Python                     |

---

## **📊 Project Workflow**

### **1. Data Cleaning & Preprocessing**

* Removed records with missing or invalid entries
* Parsed date columns
* Joined datasets using `customer_id` and `order_id`
* Calculated:

  * Number of orders per customer
  * Total payment value
  * Average order value
  * Last order date

---

### **2. Feature Engineering**

Created customer-level metrics such as:

* `customer_tenure`
* `total_orders`
* `total_payment_value`
* `avg_payment_value`
* `days_since_last_order`
* **Churn Label:**
  A customer is marked *churned* if they haven’t placed an order for **X** days.

---

### **3. Model Training (PySpark MLlib)**

Used the following steps:

* `VectorAssembler` for feature combining
* `StandardScaler` for normalization
* Logistic Regression model
* 70/30 train-test split

---

### **4. Model Evaluation**

Metrics used:

* **Accuracy**
* **Precision**
* **Recall**
* **F1 Score**
* **AUC (Area Under ROC)**

---

## **📁 Repository Structure**

```
├── data/
│   ├── customers.csv
│   ├── orders.csv
│   ├── order_items.csv
│   ├── order_payments.csv
│   └── final_customer_features.csv
├── notebooks/
│   └── churn_analysis_pyspark.ipynb
├── src/
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   ├── model_training.py
│   └── evaluation.py
├── README.md
└── requirements.txt
```

---

## **📈 Key Insights**

* Customers with lower order frequency show higher churn probability
* Long gaps between orders strongly correlate with churn
* Payment value patterns also influence customer retention

---

## **🚀 How to Run the Project**

1. Install requirements:

```
pip install -r requirements.txt
```

2. Start a PySpark session:

```
pyspark
```

3. Run the main pipeline:

```
python src/model_training.py
```

---

## **📌 Future Improvements**

* Try Gradient Boosting (XGBoost-LightGBM via Pandas API on Spark)
* Add RFM (Recency–Frequency–Monetary) scoring
* Deploy model using Flask or Streamlit

---

## **📧 Contact**

**Gautam Krishna**
