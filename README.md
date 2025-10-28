# 🎬 2015 Movie Data Analysis — IMDB & Metacritic Integration

This project explores how **movie budgets, critical scores, and genres** influenced box office performance in **2015**, using combined data from **IMDB** and **Metacritic**.  
It demonstrates data cleaning, merging, statistical analysis, and visualization using **Python**, **Pandas**, **Seaborn**, and **Statsmodels**.

---

## 📊 Project Overview

### 🎯 Objective
To analyze trends in movie budgets, revenue, ratings, and genres for films released in 2015, and uncover patterns that explain commercial and critical success.

### 🧩 Data Sources
- **IMDB_Pipeline_View** (from MongoDB): movie metadata, budget, gross sales, release year/month  
- **Metacritic**: critic scores and release dates  

Data is securely accessed via a **MongoDB Atlas connection** using a private JSON key (`My_Secret.json`).

---

## 🧹 Data Preparation

1. **Loaded** IMDB and Metacritic collections from MongoDB.
2. **Filtered** both datasets to include only movies released in **2015**.
3. **Converted** money strings (e.g., `"$120,000,000"`) to numeric values.
4. **Merged** both datasets on the movie title to create a unified view.
5. **Handled** missing data and formatted release dates and currency.

---

## 📈 Analyses Performed

### 1. **Budget vs Gross Sales**
- Scatter plot showing correlation between production budgets and total gross sales.
- Point color and size represent **Metacritic scores**.
- Key takeaway: higher budgets generally yield higher revenue, but mid-budget films can still achieve great success.

### 2. **Genre Performance**
- Bar chart of the **Top 10 genres by average gross sales**.
- *Sci-Fi*, *Adventure*, *Animation*, and *Family* dominate commercially.

### 3. **Release Timing**
- Scatter plot showing **budget by release month**.
- Big-budget films tend to release in **summer (May–August)** and **holiday months (November–December)** — classic blockbuster seasons.

### 4. **Statistical Modeling**
- Linear regression model predicting `gross_sales_usd` based on:
  - User ratings  
  - Budget  
  - Opening weekend revenue  
  - Votes  
  - Runtime  
- Provides insight into which variables most influence commercial success.

### 5. **Sentiment Analysis (Bonus)**
- Used the **CardiffNLP Roberta Twitter Sentiment model** to analyze text reviews.
- Mapped model output labels (`LABEL_0/1/2`) to human-readable sentiments (negative, neutral, positive).

---

## 🧮 Tools & Libraries

| Category | Libraries Used |
|-----------|----------------|
| Data Handling | `pandas`, `numpy`, `re`, `json` |
| Visualization | `matplotlib`, `seaborn` |
| Modeling | `statsmodels` |
| Sentiment Analysis | `transformers` (CardiffNLP Roberta) |
| Database | `pymongo`, `certifi` |



