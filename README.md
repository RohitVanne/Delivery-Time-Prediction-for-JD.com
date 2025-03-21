# Delivery Time Prediction for JD.com

## Overview
This repository contains the code and documentation for **BCIS 5110 Assignment 11 (Fall 2023)**, a data analysis project focused on predicting delivery times for customer orders using JD.com datasets. The project involves data exploration, preprocessing, merging, feature engineering, and training a Decision Tree regression model. The work was completed on **March 21, 2025**, as part of a Business Analytics course.

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

**Note**: Datasets are not included in this repository due to size or privacy constraints. Update file paths in the code (e.g., `C:\Assignments\BA\BAASSIGN\`) to your local data locations.

## Project Structure
