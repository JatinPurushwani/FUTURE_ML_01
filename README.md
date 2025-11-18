# **📌 AI-Powered Sales Forecasting Dashboard **

*A practical, beginner-friendly forecasting project using Python + Prophet + Power BI.*

---

## **🧭 1. Project Overview**

This project is about predicting **future retail sales** using historical data.
You’ll build a simple forecasting pipeline in Python and present the output through a clean Power BI dashboard.

This is meant to simulate how forecasting is done in real retail analytics teams—no complex math, no academic overkill. Just a clear, working solution.

---

## **🎯 2. What This Project Delivers**

By the end, this repository will contain:

* A clear and reproducible **Jupyter Notebook** for forecasting
* A **forecast_output.csv** containing dates + predictions
* A polished **Power BI dashboard** showing trends and forecasts
* A clean **README.md** explaining your approach
* A neat folder structure that looks professional

This is the exact structure companies expect from an intern-level delivery.

---

## **📂 3. Folder Structure**

This repository follows a simple, consultant-style structure:

```
FUTURE_ML_01/
│
├── data/                ← raw dataset (sales.csv)
├── notebooks/           ← Jupyter notebooks
├── output/              ← forecast_output.csv here
├── powerbi/             ← final Power BI dashboard (.pbix)
└── README.md            ← project documentation
```

Each folder has a purpose.
No clutter, no random files floating around.

---

## **📥 4. Dataset Used**

You can use any retail sales dataset, but the recommended one is:

**Retail Sales Forecasting (Kaggle)**
(Contains date + sales + optional store/category info)

Place your dataset as:

```
data/sales.csv
```

If your file uses different column names (e.g., "Date" instead of "date"), you will adjust the notebook accordingly.

---

## **⚙️ 5. Technologies Used**

| Category        | Tools                                           |
| --------------- | ----------------------------------------------- |
| Programming     | Python, Jupyter Notebook                        |
| Forecasting     | Prophet (Facebook), Scikit-learn (optional)     |
| Data Handling   | Pandas, NumPy                                   |
| Visualization   | Matplotlib (Python), Power BI (final dashboard) |
| Version Control | Git + GitHub                                    |

All widely used in real analytics teams.

---

## **📝 6. What the Notebook Will Do**

Your main notebook (`01_forecasting.ipynb`) will follow this simple workflow:

### **1. Load data**

* Read the CSV file
* Convert date column to datetime
* Sort by date

### **2. Clean & Prepare**

* Handle missing values
* Aggregate to monthly sales (retail works best monthly)
* Rename columns to Prophet format → `ds` and `y`

### **3. Forecast Model (Prophet)**

* Fit Prophet on monthly sales
* Generate future dates (next 12 months)
* Get predictions + lower/upper uncertainty intervals

### **4. Create forecast_output.csv**

This file will include:

| date | actual | forecast | lower | upper |
| ---- | ------ | -------- | ----- | ----- |

Power BI will use this file to create the dashboard.

### **5. Export**

Save the CSV to:

```
output/forecast_output.csv
```

---

## **📊 7. Power BI Dashboard Contents**

Your dashboard will include:

### **✔ Actual vs Forecast Line Chart**

The main visual comparing past sales and predicted values.

### **✔ Confidence Interval (lower–upper)**

Shows the uncertainty range.

### **✔ Seasonality View**

Month-wise trend visualization.

### **✔ KPI Cards**

* Next month forecast
* Predicted growth/decline
* Peak month
* Low month

### **✔ Filters (Slicers)**

* Date range
* Store (if dataset supports)
* Category (if dataset supports)

This makes your dashboard user-friendly for managers.

---

## **💡 8. Business Insights You Will Extract**

Your submission must include real insights like:

* Which months show strong seasonality
* Expected sales in the next 3–6–12 months
* Whether sales trend is upward or downward
* Inventory recommendations (increase/decrease)
* Which period requires higher promotional effort

These don’t need complex logic—just clear interpretation of your charts.

---

## **🚀 9. How to Reproduce This Project**

### Install required libraries:

```bash
pip install pandas numpy matplotlib prophet scikit-learn
```

### Run the notebook:

1. Open Jupyter
2. Navigate to `notebooks/`
3. Run each cell inside `01_forecasting.ipynb`
4. The final CSV appears in `output/`

### Open Power BI:

1. Load `forecast_output.csv`
2. Build visuals as described
3. Save your dashboard in `powerbi/`

---

## **📌 10. Next Steps (For Yourself)**

Once Task 1 is complete, you can improve the project by adding:

* Store-level forecasting
* Category-level forecasting
* XGBoost model for accuracy comparison
* Automated daily retraining
* Integrated APIs

None of this is required for Task 1, but useful for growth.

---

## **🤝 11. Acknowledgements**

This project is built as part of the **Future Interns Track (Task 1)**, focusing on practical forecasting skills used in real analytics roles.

---
