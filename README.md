#  House Sales Price Prediction

##  Practical Exam Project – RealAgents Case Study

I completed this project as part of a practical exam to demonstrate the end-to-end application of data analysis and supervised machine learning for predicting house sale prices. The fictional real estate company **RealAgents** wants to optimize listing prices in order to reduce time-to-sale for properties in a metropolitan area.

---

## Project Objective

RealAgents sells various types of houses in four cities: Silvertown, Riverford, Teasdale, and Poppleton. Some homes stay on the market longer than others, and the company wants to improve its pricing strategy by predicting sale prices more accurately based on house features.

---

##  Dataset Overview

The dataset contains historical sales records of houses. Key features include:

| Column Name     | Description |
|-----------------|-------------|
| `house_id`      | Unique identifier for each house |
| `city`          | City where the house is located |
| `sale_price`    | Final selling price in dollars |
| `sale_date`     | Date when the house was sold |
| `months_listed` | Number of months the house was listed before selling |
| `bedrooms`      | Number of bedrooms |
| `house_type`    | House category (Terraced, Semi-detached, Detached) |
| `area`          | House size in square meters |

---

##  Data Cleaning & Preparation

Key preprocessing steps included:
- Replacing missing `city` values (denoted by `'--'`) with `'Unknown'`
- Removing rows with missing `sale_price`
- Filling missing `sale_date` with `2023-01-01`
- Filling missing numerical columns (`months_listed`, `bedrooms`, `area`) with their respective mean values
- Standardizing `house_type` values and imputing missing entries with the most frequent category
- Stripping units like `' sq.m.'` from the `area` column and converting to float

Final cleaned data was stored in a DataFrame called `clean_data`.

---

##  Exploratory Analysis

To investigate whether the number of bedrooms affects price, we calculated:

- **Average Sale Price** by `bedrooms`
- **Variance of Sale Price** by `bedrooms`

```text
| Bedrooms | Avg Price | Price Variance |
|----------|-----------|----------------|
|    2     |  67,076.4 | 5.65e+08       |
|    3     | 154,665.1 | 2.38e+09       |
|    4     | 234,704.6 | 1.72e+09       |
|    5     | 301,515.9 | 2.48e+09       |
|    6     | 375,741.3 | 3.92e+09       |
