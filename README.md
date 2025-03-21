# Delivery Time Prediction for JD.com

## Overview
This repository contains the code and documentation for **Delivery Time Prediction for JD.com**, a data analysis project focused on predicting delivery times for customer orders using JD.com datasets. The project involves data exploration, preprocessing, merging, feature engineering, and training a Decision Tree regression model.

## Objective
The goal is to develop models that accurately predict delivery times for JD.com customer orders by:
- Exploring and cleaning five datasets (Order, User, Delivery, Inventory, Network).
- Merging and aggregating data into a unified dataset.
- Engineering features and training a Decision Tree regression model.
- Evaluating model performance using Root Mean Squared Error (RMSE).

## Datasets
The analysis leverages five JD.com CSV files:
1. **Order**: Order details (e.g., `order_ID`, `user_ID`, `sku_ID`, `promise`).
   - Observations: 549,989
   - Columns: 17
2. **User**: User demographics (e.g., `user_ID`, `gender`, `age`).
   - Observations: 457,298
   - Columns: 10
3. **Delivery**: Delivery details (e.g., `order_ID`, `ship_out_time`, `arr_time`).
   - Observations: 293,229
   - Columns: 6
4. **Inventory**: Inventory data (e.g., `dc_ID`, `sku_ID`, `date`).
   - Observations: 136,079
   - Columns: 3
5. **Network**: Network data (e.g., `region_ID`, `dc_ID`).
   - Observations: 56
   - Columns: 2

**Note**: Datasets are not included in this repository due to size. Update file paths in the code to your local data locations.

## Project Structure
```
Delivery-Time-Prediction-JD/
│
├── data/                  # Placeholder for datasets (not included)
│   ├── order.csv
│   ├── user.csv
│   ├── delivery.csv
│   ├── inventory.csv
│   └── network.csv
│
├── notebooks/             # Analysis scripts
│   └── Delivery Time Prediction for JD.com.ipynb # Main Jupyter Notebook
│
├── README.md              # This file
└── requirements.txt       # Python dependencies
```
## Dependencies
Install the required Python libraries:
pandas
numpy
matplotlib
seaborn
scikit-learn

Install via pip:
```bash
pip install -r requirements.txt
```
## Methodology

### 1. Data Exploration
- Loaded datasets into pandas DataFrames.
- Checked for missing values (none found) and explored key variables like `promise`.

### 2. Data Preprocessing
- Analyzed `promise` values (e.g., `-` as a placeholder) and their distribution.
- Sorted and examined `type` and `promise` relationships.

### 3. Data Merging
- Inner merge of Order and Delivery tables (326,862 rows).
- Right merge to retain all delivery records (326,880 rows).

### 4. Feature Engineering
- Aggregated order data by `order_ID` (e.g., sum of `quantity`, count of `sku_ID`).
- Merged with User data.
- Added features: `dis_rate` (discount rate), `busy_hour` (peak hour indicator).

### 5. Modeling
- Target: `delivery_time`.
- Features: `type_x`, `sku_ID`, `quantity`, `finalValue`, `gift_item`, `plus`, `dis_rate`, `busy_hour`.
- Split data: 80% training, 20% testing.
- Trained a Decision Tree Regressor and made predictions.

## Key Findings
- The promise variable’s - value (208,583 occurrences) likely indicates missing delivery commitments.
- Inner merge showed incomplete matching between orders and deliveries.
- Right merge preserved all delivery records.
- Model training was completed, but RMSE evaluation is pending in the provided document.
