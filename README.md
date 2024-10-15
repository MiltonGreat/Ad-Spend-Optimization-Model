# Social Media Advertising Campaign Optimization

This project aims to optimize advertising budget allocation across multiple channels (e.g., Facebook, Instagram, Twitter, Pinterest) and predict the return on investment (ROI) using machine learning models such as Linear Regression, Random Forest, and XGBoost. Additionally, optimization techniques such as genetic algorithms and the Scipy library's `minimize` function are used to allocate the advertising budget to maximize ROI.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Objectives](#objectives)
- [Key Features](#key-features)
- [Project Workflow](#project-workflow)
  - [Data Preprocessing](#data-preprocessing)
  - [Feature Engineering](#feature-engineering)
  - [Modeling and Predictions](#modeling-and-predictions)
  - [Optimization for Budget Allocation](#optimization-for-budget-allocation)
- [Usage](#usage)
- [License](#license)

## Overview

The project involves analyzing data from a social media advertising campaign to:
1. Predict ROI using machine learning models.
2. Optimize the allocation of a fixed advertising budget across multiple social media channels to maximize ROI.
3. Perform sensitivity analysis to study how changing the budget affects ROI.

## Dataset

The dataset contains details on social media advertising campaigns, including:
- **Clicks**: Number of clicks on the ad.
- **Impressions**: Number of times the ad was shown.
- **Engagement Score**: A score representing how engaged users were with the ad.
- **Conversion Rate**: The rate at which users clicked and then converted (e.g., made a purchase).
- **Acquisition Cost**: Cost associated with acquiring customers.
- **Total Spend**: Total budget spent on the campaign.

Additional categorical features include:
- **Target Audience**, **Campaign Goal**, **Channel Used**, **Location**, **Language**, **Customer Segment**, **Company**.

## Objectives

- **Analyze the advertising campaign performance** and identify the most effective channels.
- **Optimize the advertising budget allocation** using various optimization techniques to maximize ROI.
- **Compare different machine learning models** for predicting ROI and select the best performing model.
- **Provide insights** into the performance of different social media channels.

## Key Features

1. **Data Preprocessing**: Cleaning missing data, handling outliers, and transforming features.
2. **Feature Engineering**: Creating new features such as `CPA`, `ROAS`, `CTR`, and `Engagement_Rate` to enhance predictive modeling.
3. **Exploratory Data Analysis (EDA)**: Visualizing campaign performance metrics across channels.
4. **Machine Learning Models**: Training and evaluating multiple models including Linear Regression, Random Forest, and XGBoost to predict ROI.
5. **Optimization**: Using Scipy's `minimize` and genetic algorithms to find the optimal budget allocation across channels.

## Project Workflow

### Data Preprocessing
- **Loading and inspecting the dataset**: The dataset is extracted from a zip file and loaded into a DataFrame.
- **Handling missing values and duplicates**: Missing values are filled, duplicates are removed, and currency columns are cleaned (e.g., `Acquisition_Cost`).
- **Outlier detection**: Detecting and analyzing potential outliers in key numerical features.
  
### Feature Engineering
- **Derived features**: 
  - **Cost per Acquisition (CPA)**: `Acquisition_Cost` / (Conversion Rate * Clicks)
  - **Return on Ad Spend (ROAS)**: (Revenue generated from campaign) / (Total campaign spend)
  - **Click-Through Rate (CTR)**: Clicks / Impressions
  - **Engagement Rate**: Engagement Score / Impressions
  - **Customer Lifetime Value (CLTV)**: Estimated using conversion rate, total spend, and engagement rate.
  
### Modeling and Predictions
- **Machine learning models**: 
  - **Linear Regression**, **Random Forest Regressor**, and **XGBoost Regressor** are trained to predict ROI based on features such as Total Spend, Impressions, Clicks, Conversion Rate, etc.
  - **Cross-validation** is used to assess model performance, and key metrics such as Mean Squared Error (MSE) and R² are reported.
  
### Optimization for Budget Allocation
- **Optimization techniques**: 
  - **Genetic Algorithm**: Used to optimize budget allocation across multiple channels.
  - **Scipy's `minimize` function**: Optimizes total ROI subject to budget constraints.
  - **Sensitivity analysis**: Study how changes in budget allocation affect ROI.

#### Code Overview:

The code is designed to:
1. **Load and clean data** from a social media advertising campaign.
2. **Feature engineering** to create new metrics like `CPA`, `ROAS`, `CTR`, `Engagement_Rate`, and `CLTV`.
3. **Data visualization** to explore channel performance through bar charts, scatter plots, and heatmaps.
4. **Train machine learning models** (Linear Regression, Random Forest, XGBoost) to predict ROI based on key features.
5. **Optimize budget allocation** using both a genetic algorithm and Scipy's optimization methods.
6. **Perform sensitivity analysis** to understand how budget allocation impacts ROI.

#### Key Insights Based on the Output:

1. **Channel Performance Summary**:
   - **Facebook**, **Instagram**, **Pinterest**, and **Twitter** have similar total spend values but differ slightly in their **CPA** (Cost Per Acquisition), **CTR** (Click-Through Rate), and **Conversion Rates**.
   - **Twitter** has the highest **Conversion Rate** (0.08036) while **Pinterest** has the lowest **CTR** (0.77525).

2. **Optimized Budget Allocation**:
   - Using **Scipy's `minimize` function**, the optimal budget allocation found was:
     - Facebook: $31,568.17
     - Instagram: $15,800.32
     - Twitter: $21,039.91
     - Pinterest: $31,591.60
   - The total ROI resulting from this allocation is **$68,421.05**.

3. **Machine Learning Model Performance**:
   - **Linear Regression** yielded a low **R² score** of 0.29, indicating it struggles to capture the variance in the ROI.
   - **Random Forest Regressor** also underperformed with an **R² score** of 0.11.
   - **XGBoost Regressor** performed the best with an **R² score** of 0.33, making it the preferred model for predicting ROI in this scenario.

4. **Genetic Algorithm Budget Allocation**:
   - The **Genetic Algorithm** found a different budget allocation with Facebook receiving the most budget ($53,049.36). The total ROI for this allocation was higher, but the allocation was more skewed compared to the Scipy optimization.

5. **Sensitivity Analysis**:
   - The sensitivity analysis showed that small changes in the budget for **Facebook** had a relatively consistent effect on ROI, allowing for flexibility in budget allocation without dramatically affecting ROI.

#### Recommendations:
- **XGBoost** should be used for further predictive modeling as it outperforms the other models in predicting ROI.
- **Scipy's optimization** provides a balanced budget allocation across channels, while **genetic algorithms** may provide more aggressive allocations. Depending on the risk appetite, you can choose either method.
- **Sensitivity analysis** shows that adjusting the Facebook budget provides flexibility without significantly affecting the ROI, so you can consider reallocating small amounts from Facebook to other channels for further experimentation.

### Source:

https://www.kaggle.com/datasets/jsonk11/social-media-advertising-dataset
