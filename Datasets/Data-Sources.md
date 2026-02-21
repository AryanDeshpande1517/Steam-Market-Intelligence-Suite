# 📂 Dataset Documentation

## Steam Games Dataset (March 2025)

**Source:** Kaggle  
https://www.kaggle.com/datasets/artermiloff/steam-games-dataset  

This dataset contains comprehensive marketplace data for 90K+ Steam games, including:

- Game Title
- Price
- Required Age
- Release Date
- Developer
- Publisher
- Supported Platforms (Windows, macOS, Linux)
- User Reviews
- Playtime Metrics
- Metacritic Score
- Achievements
- DLC Count

## 📁 Original Dataset Structure

The dataset was provided in structured CSV format, containing:

- Game-level attributes
- Pricing data
- Review statistics
- Platform support indicators
- Genre and developer metadata

## ⚙️ Data Preparation Process

Before modeling in Power BI, the dataset underwent:

- Column standardization  
- Null value handling  
- Data type corrections  
- Boolean normalization (Windows / macOS / Linux)  
- Derived classification fields  
- Price segmentation (Free vs Premium)  
- Age rating categorization  

All cleaning and transformation steps were performed using:

- Power Query  
- DAX calculated columns and measures  

## 🧩 Modeling Preparation

After cleaning, the dataset was structured for:

- Platform segmentation analysis  
- Developer benchmarking  
- Genre-level aggregation  
- Revenue and pricing insights  
- Sentiment analysis  
- Storefront-level drill-through  

The model follows a Star Schema design optimized for interactive analysis.

## ⚠️ Licensing & Redistribution

This repository does **not redistribute the original dataset files** due to Kaggle licensing restrictions.

To reproduce this project:

1. Download the dataset directly from Kaggle.
2. Load the CSV file into Power BI.
3. Apply the transformations and DAX logic documented in `Scripts/DAX-Measures.md`.
4. Recreate visuals as structured in the dashboard.

## 📊 Dataset Summary

- Total Games: 90,000+  
- Total Reviews: 118M+  
- Platforms Covered: Windows, macOS, Linux  
- Pricing Model: Free-to-Play & Premium  

This dataset enables full-scale gaming market intelligence analysis.