# MetBrains DATAX Capstone — Retail Sales & Profit Analysis

![Certificate](MetBrains_Training_.pdf)

> **MetBrains DATAX — Data Analytics Training & Applied Experience**  
> Completed by **Souvik Mitra** | Certified by Data Analytics Professor Anjali

---

## Project Overview

A full-cycle data analytics project on a multi-country retail dataset, covering data cleaning, exploratory data analysis (EDA), and predictive modelling using Python and Tableau.

The dataset spans transactions across 6 product categories, 5 countries, multiple customer segments, and two sales channels (Online / Offline).

---

## Repository Structure

```
├── MetBrains_Capstone_Fixed.ipynb          # Main analysis notebook (cleaned & fixed)
├── Capstone_Metbrains_dataset.csv          # Original raw dataset
├── Capstone_Metbrains_dataset_corrected.csv  # Cleaned dataset (output of notebook)
├── Tableau_Metbrains_dataset_analysis.twb  # Tableau dashboard workbook
├── MetBrains_Training_.pdf                 # Completion certificate
└── README.md
```

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python (Pandas, NumPy) | Data cleaning & wrangling |
| Matplotlib, Seaborn | Exploratory visualisation |
| Scikit-learn | Predictive modelling |
| Tableau | Interactive dashboard |

---

## What Was Done

### 1. Data Cleaning
- Identified and corrected category–subcategory mismatches (e.g. "Phones" miscoded under wrong category) using a vectorised Pandas map
- Fixed `Order_Date` dtype from object to `datetime64`
- Verified no missing values or duplicate rows

### 2. Exploratory Data Analysis
- **Distribution analysis** — histograms and box plots for Sales and Profit
- **Outlier detection** — IQR method; no sales outliers, several profit outliers identified and profiled
- **Correlation heatmap** — Sales vs Profit (r = 0.30), Discount vs Profit (negative relationship)
- **Time trends** — yearly and quarterly Sales & Profit line plots; Q3/Q4 consistently outperform
- **Category & country breakdown** — Furniture leads in revenue; Electronics leads in profit margin; India is the top market
- **Sales channel comparison** — Offline slightly edges Online on both Sales and Profit
- **Profit margin analysis** — Overall average ~9.37%; broken down by Segment, Category, and Country

### 3. Predictive Modelling

| Model | Features | R² Score |
|---|---|---|
| Linear Regression | Sales, Quantity, Discount | ~0.09 |
| Linear Regression (expanded) | + Category, Country, Segment, Channel, Payment | improved |
| Decision Tree Regressor | All expanded features | best fit |

- One-Hot Encoding applied to categorical features via `ColumnTransformer`
- Train/test split: 80/20, `random_state=42`
- Evaluation metrics: MAE, MSE, RMSE, R²
- Actual vs Predicted scatter plots for all models

---

## Key Findings

- **Furniture** generates the most revenue but **Electronics** is most profitable per unit sold
- **Heavy discounting correlates with losses** — profit drops sharply beyond moderate discount levels
- **Q3 and Q4** are the strongest quarters across almost all categories
- **India** is the highest-revenue and highest-profit country in the dataset
- **Offline channel** marginally outperforms Online on both metrics

---

## How to Run

1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/metbrains-capstone.git
cd metbrains-capstone
```

2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

3. Launch the notebook
```bash
jupyter notebook MetBrains_Capstone_Fixed.ipynb
```

> **Note:** Place `Capstone_Metbrains_dataset.csv` in the same directory before running. The notebook will generate the corrected CSV automatically.

---

## Tableau Dashboard

Open `Tableau_Metbrains_dataset_analysis.twb` in Tableau Desktop (or Tableau Public) for the interactive dashboard version of the analysis.

---

## Certificate

Awarded upon successful completion of the **DATAX — Data Analytics Training & Applied Experience** programme under MetBrains.

---

*Built as part of the MetBrains one-month intensive data analytics bootcamp.*
