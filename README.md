# Social Media Advertising Campaign Optimization

This project aims to optimize advertising budget allocation across multiple channels (e.g., Facebook, Instagram, Twitter, Pinterest) and predict the return on investment (ROI) using machine learning models such as Linear Regression, Random Forest, and XGBoost. Additionally, optimization techniques such as genetic algorithms and the Scipy library's `minimize` function are used to allocate the advertising budget to maximize ROI.

## Overview

The project involves analyzing data from a social media advertising campaign to:

1. Predict ROI using machine learning models.
2. Optimize the allocation of a fixed advertising budget across multiple social media channels to maximize ROI.
3. Perform sensitivity analysis to study how changing the budget affects ROI.

## Dataset
The dataset used in this project is extracted from a ZIP file containing CSV files with the following columns:

- Campaign_ID: Unique identifier for the campaign.
- Target_Audience: Demographics targeted by the campaign.
- Campaign_Goal: Objective of the campaign (e.g., product launch, market expansion).
- Duration: Length of the campaign.
- Channel_Used: Advertising channel used for the campaign.
- Conversion_Rate: The percentage of users who took the desired action.
- Acquisition_Cost: Cost incurred to acquire a customer.
- ROI: Return on investment for the campaign.
- Location: Geographical location of the target audience.
- Language: Language of the target audience.
- Clicks: Number of clicks generated by the campaign.
- Impressions: Number of times the ad was displayed.
- Engagement_Score: Score measuring engagement from the target audience.
- Customer_Segment: Segment of customers targeted.
- Date: Date when the campaign was run.
- Company: Name of the company running the campaign.

## Methodology

1. Load and preprocess the dataset.
2. Conduct exploratory data analysis.
3. Train various machine learning models.
4. Optimize the advertising budget allocation.

## Modeling

- Linear Regression: Used to predict ROI based on historical data.
- Random Forest: An ensemble method that improves predictive accuracy.
- XGBoost: A gradient boosting framework that is efficient and effective for prediction tasks.

The models are evaluated using metrics such as Mean Squared Error (MSE) and R-squared (R²) scores.

## Optimization

The budget optimization process involves the following:

- Objective Function: Defines the ROI prediction based on budget allocation.
- Constraints: Ensures the total budget is adhered to and a minimum budget is allocated to each channel.
- Optimization: Uses the Scipy minimize function to find the optimal budget allocation that maximizes ROI.

### Source:

https://www.kaggle.com/datasets/jsonk11/social-media-advertising-dataset
