# Azure-Based-Demand-Forecasting-Capacity-Optimization-System

**A comprehensive data analysis project focused on Azure Compute and Storage demand patterns to support infrastructure planning and cost optimization.**

---

## Overview

This project performs data preprocessing and Exploratory Data Analysis (EDA) on simulated Azure cloud usage data. By analyzing demand trends, regional usage patterns, and cost behaviors, the system aims to provide actionable insights for better cloud infrastructure planning.

### Project Objectives

* **Regional Analysis:** Analyze Azure resource demand across different geographic regions.
* **Trend Identification:** Identify usage trends and seasonality over time.
* **Capacity Planning:** Measure infrastructure capacity utilization to detect bottlenecks or waste.
* **Cost Analysis:** Study the correlation between usage units and cost.
* **External Factors:** Evaluate the impact of economic indicators (Market Demand, Internet Traffic) on cloud usage.
* **Decision Support:** Enable data-driven decisions for capacity provisioning.

---

## Tech Stack

* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Matplotlib
* **Environment:** Jupyter Notebook / Python Scripts

---

## Dataset Information

**Source File:** `Dataset.csv`

The dataset simulates Azure cloud demand featuring core internal metrics and external economic indicators.

### Data Dictionary

| Category | Variable | Description |
| :--- | :--- | :--- |
| **Core** | `Timestamp` | Date of the record (Daily). |
| | `Region` | Geographic region of the data center. |
| | `Service Type` | Type of resource (Compute or Storage). |
| | `Usage Units` | Amount of resources consumed. |
| | `Provisioned Capacity`| Total capacity available/allocated. |
| | `Cost (USD)` | Daily cost associated with usage. |
| | `Availability Percentage`| Uptime reliability metric. |
| **External** | `Economic Index` | General economic health indicator. |
| | `Market Demand Index` | Specific demand for tech/cloud services. |
| | `Internet Traffic Index` | Global or regional traffic load. |

---

## Methodology

### 1. Data Cleaning & Preparation

Raw data was processed to ensure accuracy and consistency. The cleaned dataset is exported as `Dataset_cleaned.csv`.

* **Type Conversion:** Converted `Timestamp` to datetime objects.
* **Sorting:** Ordered data chronologically.
* **Standardization:** Normalized region naming conventions.
* **Deduplication:** Removed duplicate records.
* **Imputation:**
    * Handled missing values using interpolation and forward fill (ffill).
    * Estimated missing `Cost` values based on usage data.

### 2. Feature Engineering

To evaluate infrastructure efficiency, a specific performance metric was engineered:

**Capacity Utilization (%)**

$$Capacity\ Utilization = \left( \frac{Usage\ Units}{Provisioned\ Capacity} \right) \times 100$$

### 3. Exploratory Data Analysis (EDA)

The project generates visualizations to uncover specific patterns:

* **Demand Trend:** Usage changes over time.
* **Regional Heatmaps:** Average demand by location.
* **Service Split:** Compute vs. Storage demand comparison.
* **Utilization Distribution:** Histogram of capacity usage.
* **Cost vs. Usage:** Correlation scatter plots.
* **Macro Analysis:** Economic Index vs. Demand trends.

---

## Key Insights

* **Regional Variance:** Demand varies significantly across regions, suggesting a need for region-specific scaling strategies.
* **Over-Provisioning:** Capacity utilization analysis highlights areas where provisioned resources far exceed actual usage.
* **Cost Correlation:** Cost is directly and strongly correlated with usage levels (as expected).
* **Macro Impact:** External economic indicators show a measurable influence on cloud demand fluctuations.
* **Data Quality:** Proper preprocessing (handling missing values/standardization) significantly improves analytical reliability.
