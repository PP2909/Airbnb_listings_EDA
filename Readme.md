# Airbnb Listings EDA 

## Project Overview
This project performs Exploratory Data Analysis (EDA) on a synthetic Airbnb listings dataset covering multiple cities.

The objective is to understand the factors associated with listing prices, prepare the dataset for machine learning, and build a baseline price-prediction model.

## Dataset
- 2,000 listing records
- 17 original columns
- Listing, host, location, pricing and review information
- Synthetic data, so findings illustrate the analysis process and are not real market insights

## Technologies Used
- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Project Workflow
1. Understanding the Dataset
2. Data Cleaning
3. Outlier Detection
4. Pattern Identification
5. Relationship Analysis
6. Data Visualization
7. Machine Learning Data Preparation

## Data Cleaning Decisions
- Missing `reviews_per_month` and `last_review` values (63) matched listings with 0 reviews, so they were filled with 0.
- Missing `review_score` values (303) all belonged to listings with 2 or fewer reviews, so they were kept and a `has_review_score` flag was added.
- Missing neighbourhoods were labelled "Unknown" instead of using the most common value.
- Prices are in 7 different local currencies, so a price index (price divided by the city's median price) was created for fair comparison. No currency conversion was done.
- Price is skewed (about 2.0), so it was log-transformed for modelling. The 66 price outliers were kept because they look like genuine luxury listings.

## Key Findings
- Room type is the strongest driver of price. Median price index is about 1.6 for hotel rooms, 1.3 for entire homes, 0.6 for private rooms and 0.35 for shared rooms.
- Number of guests (`accommodates`) shows a weak-to-moderate positive correlation with price (r ≈ 0.29), largely explained by room type.
- Reviews, ratings and availability show almost no relationship with price.

## Machine Learning Preparation
- Missing values handled
- Categorical variables encoded
- Input features and log-transformed price target selected
- Dataset split into training and testing data

## Baseline Model
- A Random Forest regressor reached R² ≈ 0.39, a moderate result.
- Permutation importance was used instead of built-in feature importance, which wrongly ranked `availability_365` highly.

## Project Status
EDA completed. Dataset prepared for machine learning. A baseline Random Forest model has been trained; further tuning is possible.

## How to Run
1. Open `Airbnb_Listings_EDA.ipynb` in Google Colab.
2. Run the first cell and upload `airbnb_listings_eda_synthetic.csv` when prompted.
3. Run the remaining cells in order (Runtime → Run all).

## Author
PRAGYA SINHA