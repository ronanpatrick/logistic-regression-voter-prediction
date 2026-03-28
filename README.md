# Voter Turnout Classification (Logistic Regression) 

## Project Overview
This project builds a Machine Learning classifier to predict whether an individual is a "Voter" or "Non-voter" based on demographic features. It demonstrates a complete end-to-end data science pipeline: fetching data programmatically via API, performing complex feature engineering (Ordinal and One-Hot Encoding), and training a Logistic Regression model.

## Dataset
* **Source:** `ulrikthygepedersen/voters-and-non-voters` (Pulled programmatically via Kaggle API)
* **Features Used (X):** `educ` (Education), `income_cat` (Income), `race`, `gender`
* **Target Variable (y):** `voter_category` 

## Tech Stack
* **Language:** Python
* **Data Ingestion:** `kagglehub`
* **Data Manipulation:** Pandas
* **Feature Engineering:** Scikit-Learn (`OrdinalEncoder`, `OneHotEncoder`)
* **Machine Learning:** Scikit-Learn (`linear_model.LogisticRegression`)
* **Data Visualization:** Matplotlib

## Workflow & Methodology
1. **Programmatic Data Ingestion:** Utilized `kagglehub` to directly download the latest dataset, ensuring high reproducibility without needing local CSV files.
2. **Feature Engineering Pipeline:** * **Ordinal Encoding:** Applied to hierarchical categories like `educ` (High school -> College) and `income_cat` (Less than $40k -> $125k or more).
   * **One-Hot Encoding:** Applied to nominal categories like `race` and `gender` to prevent the model from inferring false mathematical rankings.
3. **Data Cleaning:** Concatenated the newly engineered categorical features, dropped the raw redundant columns, and handled missing values (`NaN`).
4. **Model Training:** Fit a Logistic Regression classifier to predict the discrete categorical target variable.
5. **Interactive Prediction:** Included a user-input script allowing real-time predictions based on custom demographic inputs.

## How to Run

### Option 1: Run in Cloud (Recommended)
You can view and run this notebook instantly in your browser using Google Colab. The dataset will automatically download to your session via the Kaggle API.
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ronanpatrick/logistic-regression-voter-prediction/blob/main/Logistic_Regression_voter.ipynb)

### Option 2: Run Locally
1. Clone this repository: `git clone https://github.com/ronanpatrick/logistic-regression-voter-prediction.git`
2. Install the required libraries: `pip install pandas scikit-learn matplotlib kagglehub`
3. Open the `.ipynb` file in Jupyter Notebook or VS Code and run all cells.
