# SQL---EDA---Layoffs
Exploratory Data Analysis (EDA) project using SQL on a real-world layoffs dataset. Cleaned, transformed, and analyzed company layoff trends by industry, country, time, and more using advanced SQL techniques.


# 📊 SQL Layoffs EDA Project

This project performs **Exploratory Data Analysis (EDA)** using **SQL** on a real-world layoffs dataset. The goal is to uncover insights about company layoffs over time, by country, industry, and other factors.

---

## 📁 Dataset
The dataset was sourced from a public CSV file listing major tech layoffs. It includes columns such as:

- `company`
- `location`
- `industry`
- `total_laid_off`
- `percentage_laid_off`
- `date`
- `stage`
- `country`
- `funds_raised_millions`

---

## 🧹 Data Cleaning Steps

The data was cleaned in multiple steps using SQL:

1. **Removed Duplicates**  
   - Used `ROW_NUMBER()` with `PARTITION BY` to identify and delete duplicate rows.

2. **Standardized Values**  
   - Trimmed whitespaces
   - Merged similar text values (e.g., `United States`, `United States.` → `United States`)
   - Converted `date` column from text to `DATE` type

3. **Handled Missing or Null Values**  
   - Populated missing `industry` values using self-join on company names
   - Removed rows with no `total_laid_off` and `percentage_laid_off` values

4. **Dropped Unnecessary Columns**  
   - Removed the helper column `row_num` after cleaning

---

## 📊 Exploratory Analysis Performed

- 🔢 Max layoffs and max percentage laid off  
- 🏢 Companies with most layoffs  
- 🏭 Industries and 🗺️ Countries with highest layoffs  
- 📆 Timeline analysis: by year, month, and rolling totals  
- 🥇 Top 5 companies by layoffs per year  
- 📉 Layoff trends over time

---

## 🧠 Key SQL Concepts Used

- `ROW_NUMBER()` and `DENSE_RANK()` window functions  
- `GROUP BY`, `ORDER BY`, `SUM()`, `MAX()`  
- Common Table Expressions (CTEs)  
- Substring date extraction for monthly and yearly trends  
- Self-joins for NULL value imputation

---

## ⚙️ Tech Stack

- 💾 PostgreSQL (Docker)
- 🛠️ DBeaver for SQL IDE
- 🐧 Ubuntu WSL for container and terminal access

---

## 📷 Sample Insights

> 📈 **2023 had the highest layoffs**, dominated by the tech sector  
> 🇺🇸 **United States** had the largest number of layoffs  
> 🏭 **Consumer, Retail, and Crypto industries** saw frequent layoffs  
> 🥇 Top companies laying off the most: Amazon, Meta, Google

---

## 🚀 How to Reproduce

1. Clone this repo  
2. Import the `CSV` into PostgreSQL (instructions included)  
3. Run the SQL scripts step-by-step in DBeaver or any SQL tool  
4. Modify queries as needed for your own analysis

---

