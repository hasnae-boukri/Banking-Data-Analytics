# 🏦 Banking Data Analytics: End-to-End Project

An **end-to-end data analytics project** simulating real-world banking scenarios.
This project analyzes customer transactions to uncover insights such as **spending patterns**, **fraud detection**, and **customer segmentation**.

Built with:

* 🐍 **Python** for data processing & machine learning
* 🗃️ **MySQL** for database management
* 📊 **Power BI** for interactive visualizations

---

## 📚 Table of Contents

* [Overview](#overview)
* [Features](#features)
* [Project Structure](#project-structure)
* [Installation & Setup](#installation--setup)
* [Usage](#usage)
* [Key Insights & Results](#key-insights--results)
* [Screenshots](#screenshots)
* [Technologies](#technologies)
* [Scalability & Future Work](#scalability--future-work)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)

---

## 🧠 Overview

In the banking sector, analyzing transaction data is essential for **risk management**, **customer personalization**, and **fraud prevention**.

This project processes **10,000+ fictional transactions** (generated with realistic patterns) to:

* Clean and store data in a relational database (MySQL)
* Perform exploratory data analysis (EDA)
* Build a simple ML model to predict fraud
* Create interactive Power BI dashboards for stakeholders

💡 **Business Value:**
Identifies high-risk customers (e.g., 15% of nighttime transactions flagged as fraud) and suggests targeted marketing for premium clients.

📊 Data is anonymized and fictional — inspired by Kaggle’s *Credit Card Fraud Detection* dataset.

---

## ⚙️ Features

✅ **ETL Pipeline** – Extract (CSV/SQL), Transform (clean & engineer features with Pandas), Load (to MySQL)
✅ **SQL Data Modeling** – Multi-table schema for customer-account-transaction analysis
✅ **EDA in Python** – Visualizations, descriptive stats, anomaly detection
✅ **Machine Learning** – Random Forest for fraud detection (≈85% accuracy)
✅ **Power BI Dashboard** – KPIs, slicers, maps & DAX measures
✅ **Automation** – Data generation & batch insertion scripts
✅ **Documentation** – Notebooks with explanations & insights

---

## 🗂️ Project Structure

```
Banking-Data-Analytics-End-to-End/
├── README.md
├── LICENSE
├── requirements.txt
├── .env.example
├── data/
│   ├── raw_transactions.csv
│   └── cleaned_data.csv
├── notebooks/
│   ├── 01_data_ingestion.ipynb
│   ├── 02_eda_analysis.ipynb
│   ├── 03_fraud_detection_ml.ipynb
│   └── 04_insights_summary.ipynb
├── sql/
│   ├── create_database.sql
│   ├── create_tables.sql
│   └── sample_queries.sql
├── powerbi/
│   ├── Banking_Dashboard.pbix
│   └── dashboard_screenshots/
├── reports/
│   └── executive_summary.pdf
└── scripts/
    ├── generate_data.py
    └── etl_pipeline.py
```

---

## 🧩 Installation & Setup

### Prerequisites

* Python 3.8+
* MySQL Server 8.0+
* Power BI Desktop (free)
* Git

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/Banking-Data-Analytics-End-to-End.git
cd Banking-Data-Analytics-End-to-End
```

### 2️⃣ Set Up Python Environment

```bash
python -m venv venv
source venv/bin/activate       # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3️⃣ Configure Environment Variables

Copy `.env.example` to `.env` and edit:

```
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=banking_db
```

### 4️⃣ Set Up Database

```bash
mysql -u root -p < sql/create_database.sql
mysql -u root -p banking_db < sql/create_tables.sql
```

### 5️⃣ Generate & Load Data

```bash
python scripts/generate_data.py
python scripts/etl_pipeline.py
```

### 6️⃣ Power BI Connection

1. Open `powerbi/Banking_Dashboard.pbix`
2. Connect to MySQL (use `.env` credentials)
3. Refresh data and explore!

> 💡 Tip: If MySQL connection fails, check port 3306 or Docker config.

---

## 🧮 Usage

### Run EDA & ML

```bash
jupyter notebook
```

Then run:

1. `01_data_ingestion.ipynb`
2. `02_eda_analysis.ipynb`
3. `03_fraud_detection_ml.ipynb`

Expected Output:

> Fraud detection accuracy ≈ 85%, main drivers: transaction amount & time of day.

### Run SQL Queries

```sql
SELECT c.customer_name, SUM(t.amount) AS total_spent
FROM customers c
JOIN transactions t ON c.id = t.customer_id
GROUP BY c.id
HAVING total_spent > 10000
ORDER BY total_spent DESC;
```

---

## 📈 Key Insights & Results

* **Transaction Trends:** Withdrawals peak at month-end (~40%)
* **Customer Segmentation:** Top 10% clients = 60% of deposits
* **Fraud Detection:** 15% transactions flagged as high-risk

  * Precision: 82%, Recall: 88%

**Business Recommendations:**

* Implement 2FA for nighttime transactions
* Promote savings products to young customers
* Potential 10–15% fraud reduction overall

Full report: `reports/executive_summary.pdf`

---

## 🖼️ Screenshots

| Power BI Dashboard                 | ML Feature Importance                      | SQL Query Example             |
| ---------------------------------- | ------------------------------------------ | ----------------------------- |
| ![Dashboard](images/dashboard.png) | ![Features](images/feature_importance.png) | ![SQL](images/sql_result.png) |

> Upload screenshots to `/images/` and update the links above.

---

## 🧰 Technologies

| Category            | Tools                                                             |
| ------------------- | ----------------------------------------------------------------- |
| **Languages**       | Python, SQL                                                       |
| **Libraries**       | Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, MySQL Connector |
| **Tools**           | Jupyter Notebook, MySQL Workbench, Power BI Desktop               |
| **Data Generation** | Faker                                                             |
| **Version Control** | Git                                                               |

---

## 🚀 Scalability & Future Work

* Currently handles **10K records locally**
* **Future Enhancements:**

  * Deploy database on AWS RDS
  * Add Isolation Forest / deep learning models
  * Schedule ETL with Apache Airflow
  * Publish dashboards to Power BI Service

---

## 🤝 Contributing

Contributions are welcome!
Fork the repo, create a feature branch, and submit a Pull Request.

Focus areas:

* 🪲 ETL or ML improvements
* 📊 New dashboards
* 🧾 Better documentation

> Follow **PEP8** guidelines for Python code.

---

## 📜 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 📬 Contact

**Hasnae Boukri** – [your.email@example.com](boukrii.hasnaee@gmail.com)
🔗 [LinkedIn]((https://www.linkedin.com/in/hasnae-boukri/))
🌐 [Project Link](https://github.com/YOUR_USERNAME/Banking-Data-Analytics-End-to-End)

---
