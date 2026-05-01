# Datathon 2026: The Gridbreaker - Vietnamese Fashion E-commerce 

This repository contains the code and analysis for the **Datathon 2026: The Gridbreaker** competition, hosted by Vin Telligence and the Vin University Data Science & AI Club[cite: 3]. The project focuses on transforming raw data into actionable business solutions for a Vietnamese fashion e-commerce enterprise[cite: 1, 3].

## 📌 Project Overview

The objective of this project is to analyze operational, analytical, and transactional data from July 4, 2012, to December 31, 2022, to extract business-relevant insights and build a robust forecasting model[cite: 3]. 

The repository is structured around the competition's core requirements, blending economic strategy with machine learning to optimize inventory, plan promotions, and manage logistics[cite: 1, 3].

## 🗂️ Repository Structure

### 1. Part 2: Ecommerce Business Intelligence & Strategy EDA
**File:** `DATATHON_821_Part_2_Final.ipynb`

This section focuses on moving the business from pure growth to profitable demand[cite: 1]. It includes:
*   **Data Quality Audit:** Rigorous checks on missingness, duplicates, and schema integrity across all 15 provided tables[cite: 1].
*   **Semantic Layer Construction:** Reconstructing the commercial layer to analyze orders, net revenue, refunds, and gross margins to identify profitable versus leaky demand streams[cite: 1].
*   **Executive Storyline:** Descriptive and diagnostic analytics exploring historical growth, market shocks, recovery periods, and calendar seasonality[cite: 1].
*   **Actionable Insights:** Translating data patterns into prescriptive strategic decisions (e.g., category performance, segment analysis, and promotion impact)[cite: 1].

### 2. Part 3: Sales Forecasting Pipeline
**File:** `DATATHON_821_Part_3_Final.ipynb`

An end-to-end machine learning pipeline designed to forecast daily `Revenue` (primary target) and `COGS` for the test period of January 1, 2023, to July 1, 2024[cite: 2, 3]. 
*   **Feature Engineering:** Utilizing rolling windows and lag features (e.g., 7, 14, 28, 365 days) to capture both short-term volatility and long-term seasonality[cite: 2].
*   **Leakage Prevention:** Strict utility functions to ensure no unshifted operational features or future targets leak into the training data[cite: 2].
*   **Modeling:** Leveraging an ensemble of models including `HistGradientBoostingRegressor`, `RandomForestRegressor`, `ExtraTreesRegressor`, `Ridge`, and `HuberRegressor`[cite: 2].
*   **Evaluation:** Models are cross-validated and optimized to minimize Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE), while maximizing the coefficient of determination ($R^2$)[cite: 3].

## 📊 Dataset Description

The analysis is built on a highly relational database consisting of 15 CSV files grouped into four layers[cite: 3]:
*   **Master Data:** `products.csv`, `customers.csv`, `promotions.csv`, `geography.csv`[cite: 3].
*   **Transaction Data:** `orders.csv`, `order_items.csv`, `payments.csv`, `shipments.csv`, `returns.csv`, `reviews.csv`[cite: 3].
*   **Analytical Data:** `sales.csv` (training data for revenue) and `sample_submission.csv`[cite: 3].
*   **Operational Data:** `inventory.csv` (monthly stock snapshots) and `web_traffic.csv`[cite: 3].

*(Note: In accordance with competition rules, no external data was used to train the models or generate insights[cite: 3].)*

## 🚀 How to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/datathon-2026-gridbreaker.git
   cd datathon-2026-gridbreaker
   ```
2. **Install dependencies:**
   Ensure you have Python 3.10+ installed. 
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```
3. **Data Setup:**
   Place the 15 competition CSV files into a local `data/` directory at the root of the repository[cite: 2].
4. **Execute Notebooks:**
   * Run the EDA notebook to generate the business intelligence visualizations and semantic tables.
   * Run the Forecasting notebook. You can toggle the `RUN_MODE` to `"quick"` for rapid testing or `"full"` for a complete cross-validated training run[cite: 2]. 

## 🏆 Evaluation Metrics

The forecasting models in Part 3 are evaluated purely on Kaggle using the following metrics[cite: 3]:
*   **MAE (Mean Absolute Error):** To measure average absolute deviation[cite: 3].
*   **RMSE (Root Mean Squared Error):** To penalize large errors during volatile sales periods[cite: 3].
*   **$R^2$:** To determine the proportion of variance explained by the model[cite: 3].
```
