# Exploratory Data Analysis (EDA) - Banking Customer Case Study

This repository contains an end-to-end Exploratory Data Analysis (EDA) performed on a banking client dataset (`Banking.csv`) containing 3,000 unique client profiles. The project uncovers structural trends, evaluates demographics, maps asset distributions, and prepares the dataset for downstream modeling.

---

## 🎯 Task Objectives

Following a structured pipeline for professional data analysis, this project fulfills the following core objectives:

* **Pre-Analysis Questioning:** Formulating meaningful business and technical questions prior to running calculations.
* **Data Structure Evaluation:** Reviewing variables, data types, and underlying shapes across numerical and categorical features.
* **Trend & Pattern Identification:** Detecting specific behavioral traits, wealth patterns, and geographic distributions.
* **Hypothesis Testing & Visualization:** Utilizing descriptive statistics and rich visualizations (`seaborn`, `matplotlib`) to validate assumptions.
* **Data Quality Assessment:** Identifying potential structural anomalies, high-cardinality issues, or missing data transformations needed for downstream predictive analytics.

---

## ❓ 1. Pre-Analysis Questions

Before performing technical operations, several baseline business questions were formulated to guide the exploration:

* **Demographics & Loyalty:** How do client age, nationality, and occupation impact their assigned loyalty classification (e.g., Jade, Silver, Gold, Platinum)?
* **Financial Distribution:** What is the relationship between an individual's estimated income, credit card balances, deposits, and business loans?
* **Risk Profiling:** Are specific nationalities or income brackets associated with higher risk weightings?
* **Asset Diversification:** Do clients with multiple properties utilize foreign currency accounts or checking accounts more aggressively?

---

## 🏗️ 2. Data Structure & Features

The dataset contains **3,000 rows** and **25 columns** consisting of categorical/object representations, floats, and integers. 

### Core Features Evaluated:
* **Demographic Metrics:** `Age`, `GenderId`, `Nationality`, `Occupation`
* **Operational Attributes:** `Client ID`, `Name`, `Location ID`, `Joined Bank`, `Banking Contact`
* **Financial Asset/Liability Profiles:** `Estimated Income`, `Superannuation Savings`, `Amount of Credit Cards`, `Credit Card Balance`, `Bank Loans`, `Bank Deposits`, `Checking Accounts`, `Saving Accounts`, `Foreign Currency Account`, `Business Lending`
* **Segmentation & Classification:** `Fee Structure`, `Loyalty Classification`, `Properties Owned`, `Risk Weighting`, `Income band`

---

## 📈 3. Key Trends & Descriptive Summary

Through descriptive summary statistics (`df.describe()`) and value distribution calculations, several core trends were uncovered:

* **Loyalty Concentration:** The client base is heavily dominated by the **Jade** classification (1,331 clients), followed by Silver (767) and Gold (585). **Platinum** remains highly exclusive with only 317 accounts.
* **Regional Dominance:** Customers of **European** nationality constitute the largest demographic group (1,309 clients), followed by Asian (754) and American (507).
* **Financial Distributions:**
  * **Age:** The average client age is **51 years old**, spanning from young adults (17) to seniors (85).
  * **Income:** The mean Estimated Income hovers around **$171,305**, with high variance extending up to a maximum profile of $522,330.
  * **Liabilities:** Average Bank Loans stand at roughly **$591,386**, while Business Lending averages **$866,759**.

---

## 📊 4. Statistical Validation & Visualizations

The analysis incorporates multi-variate count plots and demographic breakdowns using `Seaborn` and `Matplotlib`:

* **Categorical Feature Distribution:** A programmatic plotting loop automatically generates distribution insights across predictors like `BRId`, `GenderId`, `Amount of Credit Cards`, `Fee Structure`, `Loyalty Classification`, and `Risk Weighting`, using `Nationality` as a visual contrast hue.
* **Income Discretization:** Estimated income was engineered into `low`, `medium`, and `high` bands, demonstrating a strong representation within the middle-class segment (1,517 medium-band earners vs. 456 high-band earners).

---

## ⚠️ 5. Data Issues & Future Recommendations

During the exploration phase, several attributes were identified that require pre-processing before applying machine learning pipelines:

* **High Cardinality:** The `Occupation` text column contains **195 unique labels**. Downstream encoding will require bucket-grouping or target encoding to minimize dimensionality.
* **Date Transformations:** Columns such as `Joined Bank` are initially parsed as `object` (string format) and need conversion to datetime format to derive a concrete "Customer Tenure" feature.
* **Anomalous Ranges:** Financial properties like `Checking Accounts` and `Saving Accounts` range down to absolute zero and possess highly skewed distributions, requiring potential logarithmic transformation or outlier handling.

---

## 🛠️ Tech Stack Used

* **Python 3**
* **Pandas** — Data manipulation and metadata parsing
* **NumPy** — Mathematical array operations
* **Matplotlib** — Custom visualization layouts
* **Seaborn** — Statistical visualization and category mapping

---
