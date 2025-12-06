# Spotify Databricks Project

## Overview

This project implements an end-to-end analytics and machine learning pipeline using Databricks and PySpark.

The objective was to load a Spotify dataset, clean and structure it, store it in Delta tables, perform SQL-based analysis, build visual dashboards, and apply a basic machine learning model to predict track popularity.

---

## Dataset

The dataset was sourced from Kaggle:  
https://www.kaggle.com/datasets/abdullahmeo/spotify-analysis-and-visualization

It contains song-level Spotify metadata, such as audio features, artist, album, duration, loudness, tempo, danceability, and popularity.

---

## Tech Stack

- Databricks
- PySpark (DataFrames + MLlib)
- Databricks SQL
- Delta tables
- Databricks Dashboards
- Databricks Jobs (Workflow scheduling)

---

## Project Workflow

### 1. Data Ingestion
The CSV file was uploaded into a Databricks Volume, loaded into a Spark DataFrame, and saved as a Delta table:

`main.pmi.spotify_clean`

### 2. Data Cleaning & Transformation
- Removed missing values  
- Eliminated duplicates  
- Casted numerical columns to `double`  
- Prepared feature vectors for ML processing

### 3. Data Storage
Cleaned data stored inside Unity Catalog as a Delta table:

- Catalog: `main`
- Schema: `pmi`
- Table: `spotify_clean`

### 4. SQL Analytics
Example analytical queries performed:
- Top artists by number of tracks  
- Top albums by number of tracks  

These insights were visualized later in dashboards.

### 5. Notebook Exploration
Exploratory analysis done via Databricks Notebook using PySpark — including statistics, schema review, and feature examination.

### 6. Dashboard Creation
A Databricks Dashboard was created containing:
- Two charts (tracks per artist, tracks per album)
- Interactive filter (e.g., filter by artist)
- Clear layout and titles

This enabled visual insight extraction.

---

## Bonus Component 1 — Automated Pipeline

A Databricks **Job** was implemented to automatically execute the main notebook on a schedule.

Although the dataset is static in this assignment,  
**the scheduled job demonstrates understanding of how real-world pipelines may refresh data from live APIs or streaming sources.**  
Thus, the mechanism (designing the automation, scheduling, and running pipelines) satisfies the learning objective of workflow automation.

---

## Bonus Component 2 — Machine Learning

A Linear Regression model was developed using PySpark MLlib to predict track popularity based on audio features:

- `energy`
- `danceability`
- `speechiness`
- `loudness`
- `tempo`
- `valence`

Workflow included:
1. Feature engineering using VectorAssembler  
2. Train/test split  
3. Model training  
4. Predictions  
5. RMSE and R² evaluation metrics

This demonstrates basic ML capability within a Databricks pipeline.

---

## Repository Contents

```
├── spotify_project_notebook.ipynb     # Full ETL + ML pipeline notebook
├── dashboard.png                      # Dashboard screenshot
├── jobs.png                        # Automation job run screenshot
└── README.md                          # Project documentation
```

---

## Final Notes

This project showcases:
- ingestion  
- cleaning  
- Delta storage  
- SQL analysis  
- dashboard creation  
- job scheduling automation  
- machine learning integration  

Together, these components form a practical portfolio-ready example of a **mini end-to-end analytics project** on Databricks
