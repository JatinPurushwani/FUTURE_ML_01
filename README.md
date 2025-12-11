# **📌 AI - Powered Retail Sales Forecasting **

A clean, practical forecasting project built with **Python + Prophet** and visualized through **Power BI**, designed for real-world retail analytics use-cases.

This project predicts **monthly store sales** using historical data from the **Rossmann Store Sales** competition on Kaggle.

---

# **📁 Project Structure**

```
FUTURE_ML_01/
│
├── data/
│     ├── train.csv
│     └── store.csv
│
├── notebooks/
│     └── 01_forecasting.ipynb
│
├── output/
│     └── forecast_output.csv
│
├── powerbi/
│     └── Rossmann_Forecast.pbix     (dashboard)
│
└── README.md
```
---

# **🎯 Objective**

Build a **forecasting system** that can help retail managers answer:

* How will sales behave in the next months?
* Are sales trending upward or downward?
* Which periods show seasonality?
* How uncertain is the forecast?
* How should inventory & staffing adjust?

---

# **🔍 Dataset**

**Source:** Rossmann Store Sales (Kaggle)
Contains:
* Daily sales
* Open/Closed indicator
* Promotions
* Store metadata
* Competitor information

For forecasting, we aggregate sales to **monthly total across all stores**.

---

# **🛠️ Tools & Technologies**

| Component     | Tools Used                        |
| ------------- | --------------------------------- |
| Forecasting   | Prophet (Facebook)                |
| Data Prep     | Pandas, NumPy                     |
| Visualization | Matplotlib, Power BI              |
| Modeling      | Scikit-learn metrics (MAE / RMSE) |
| Notebook      | Jupyter                           |
| Versioning    | Git + GitHub                      |

---

# **📌 Methodology (Short, Clear, Interview-Ready)**

### **1. Load & Merge Data**

* train.csv + store.csv
* Remove closed days (Open = 0)
* Remove zero-sales entries
* Keep only required columns

### **2. Aggregate to Monthly Series**

Daily → Monthly using:

```python
df.resample("M")["Sales"].sum()
```

Prophet prefers clean, stable monthly trends.

### **3. Train–Holdout Split**

* Last 6 months held out for evaluation
* Remaining used for training

### **4. Prophet Model**

Configured with:

* yearly_seasonality=True
* weekly_seasonality=False
* daily_seasonality=False

### **5. Evaluation**

Using MAE + RMSE.

**Final performance:**

```
MAE  = 34,977,653
RMSE = 42,483,831
```

This is expected for aggregated retail sales with large magnitudes.

### **6. Export for Power BI**

A unified CSV used by dashboard:

| date | actual | forecast | lower | upper |
| ---- | ------ | -------- | ----- | ----- |

Saved to:

```
output/forecast_output.csv
```

---

# **📊 Key Visual — Actual vs Forecast**

This line chart shows monthly sales (2013–2015) and forecast (2015–2016).

```

```


---

# **📈 What the Power BI Dashboard Includes**

The dashboard contains:

### ✔ Actual vs Forecast line chart

Shows base trend + future predictions.

### ✔ Confidence interval (lower–upper)

Represents uncertainty in the forecast.

### ✔ Seasonality view

Month-over-month pattern extracted from Prophet.

### ✔ KPI Cards

* Next month forecast
* Expected YoY change
* Highest predicted month
* Lowest predicted month

### ✔ Filters

* Date
* Store (optional)
* Promo status (optional)

Even a minimal dashboard satisfies the task.

---

# **💡 Insights From the Forecast**

Based on the aggregated Rossmann monthly sales:

* Clear **yearly seasonality**
* Sales dip mid-year and peak in Q4
* Forecast shows **moderate upward trend**
* Promotion periods match sales spikes
* Uncertainty band widens over time (normal for Prophet)
* Useful for **inventory planning**, **cashflow** and **staffing**

---

# **🚀 How to Run the Entire Pipeline**

### **1. Install dependencies**

```bash
pip install pandas numpy prophet matplotlib scikit-learn
```

### **2. Run the notebook**

```bash
notebooks/01_forecasting.ipynb
```

### **3. Get output CSV**

File generated at:

```
output/forecast_output.csv
```

### **4. Load into Power BI**

* Home → Get Data → CSV
* Select `forecast_output.csv`
* Build visuals
* Save dashboard in `powerbi/`

---

# **📌 Why Prophet? **

Prophet is ideal for:

* Business time series
* Seasonality
* Missing data
* Irregularities
* Quick deployment
* Interpretable parameters

Used by:

* Meta
* Uber
* Airbnb
* Shopify
* Walmart Analytics Teams

---

# **🤝 Acknowledgements**

This project is submitted as **Task 1** of the *Future Interns ML Track*, designed to replicate real-world forecasting workflows used in retail analytics.

---
