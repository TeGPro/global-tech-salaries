# Global Tech Salaries 2025: ETL Pipeline & Feature Engineering 🚀

## Overview
This project demonstrates a complete Data Engineering and Exploratory Data Analysis (EDA) pipeline. The goal was to take a raw, unstructured dataset of global IT salaries and transform it into a clean, normalized, and feature-rich format ready for Machine Learning modeling or BI visualization.

## 🛠 Tech Stack
* **Python** (Pandas, NumPy)
* **Data Processing:** ETL, Feature Engineering, Quantile-based clustering
* **Security Context:** Data integrity checks and sanitization

## 🧠 Pipeline Architecture

### 1. Data Cleaning & Sanitization (The "AppSec" approach)
* Removed duplicate records and handled missing values to prevent data poisoning.
* Standardized currency columns into a single `salary_in_usd` metric to ensure model consistency.

### 2. Feature Engineering
Instead of using raw, noisy data, I engineered new categorical features to improve potential ML model accuracy:
* **`job_category`**: Condensed 347 unique, messy job titles into 6 standardized business categories (e.g., Data Science, Data Engineering, ML).
* **`salary_level`**: Created a relative, context-aware metric (Low, Medium, High) using **Quantile-based binning (`pd.qcut`)** specific to each country. This prevents the model from being biased by high-GDP nations like the US.
* **`is_remote_nomad`**: A boolean flag comparing `company_location` and `employee_residence` to track global remote work trends.

## 🚀 How to Run
1. Clone the repository.
2. Run the `etl_pipeline_salaries.ipynb` notebook to reproduce the data transformation.
3. The output will be generated as `final_salaries_cleaned.csv`.

---
*Author: George Lozovoi | AI & AppSec Engineering Student (Bauman MSTU)*
