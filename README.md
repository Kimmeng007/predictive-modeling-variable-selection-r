# Predictive Modeling & Variable Selection (R Project)

This project explores **predictive modeling and variable selection techniques** using R.  
The goal is to **identify the most suitable target variable** and evaluate model performance using **forward, backward, and stepwise regression with cross-validation**.

The analysis is based on a dataset of social media post metrics and focuses on **robust preprocessing, outlier handling, and model evaluation**.

## Methodology Overview

### 1. Data Preprocessing
- Load and inspect the dataset
- Remove missing values (`NA`)
- Convert categorical variables (e.g. `Type`) into numeric form
- Explore data structure and distributions

### 2. Outlier Detection
- Outliers are detected using the **Interquartile Range (IQR)** method
- Outliers are removed **only from the target variable** during model training
- Boxplots are used for visual inspection of potential targets

### 3. Target Variable Exploration
The following variables are tested as potential targets:
- `Lifetime.Post.Total.Reach`
- `Lifetime.Post.Total.Impressions`
- `Lifetime.Engaged.Users`
- `Lifetime.Post.Consumers`
- `Lifetime.Post.Consumptions`
- `Lifetime.Post.Impressions.by.people.who.have.liked.your.Page`
- `Lifetime.Post.reach.by.people.who.like.your.Page`
- `Lifetime.People.who.have.liked.your.Page.and.engaged.with.your.post`
- `comment`
- `like`
- `share`
- `Total.Interactions`

Each target is modeled separately using the remaining variables as predictors.

## Model Building & Selection

For each target variable:
- Data is split into **80% training / 20% testing**
- Models are trained using:
  - **Forward Selection**
  - **Backward Selection**
  - **Stepwise Selection**
- Model performance is validated using **10-fold cross-validation**

## Evaluation Metrics

Custom evaluation metrics are used during cross-validation:
- **R² (Coefficient of Determination)**
- **RMSE (Root Mean Squared Error)**
- **MAPE (Mean Absolute Percentage Error)**

A custom summary function is implemented to handle zero values safely when computing MAPE.

## Technologies & Libraries

This project is implemented in **R** using the following libraries:

- `caret` – model training & cross-validation
- `glmnet` – regression utilities
- `corrplot` – correlation visualization
- `ggplot2` – data visualization
- `dplyr` – data manipulation

## How to Run the Project

1. Open `Project_final_HONG_KOH.Rmd` in RStudio
2. Make sure `dataset.csv` is available and update the file path if needed
3. Install required packages:
   ```r
   install.packages(c("caret", "corrplot", "glmnet", "ggplot2", "dplyr"))

