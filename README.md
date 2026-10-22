# Customer Churn Prediction in R

## Project Overview

This project develops a customer churn prediction model in R using the **tidymodels** framework. A stratified train/test split and cross-validation are used to evaluate model performance, while a documented preprocessing recipe prepares the data for modelling.

A **logistic regression model** is trained to estimate the probability of customer churn, with model coefficients interpreted using **odds ratios** to identify factors associated with increased or decreased churn risk.

The complete analysis is presented as a reproducible **Quarto report**.

## Objectives

- Prepare customer data for predictive modelling.
- Create a stratified training and testing dataset.
- Apply a documented preprocessing workflow.
- Use cross-validation to assess model stability.
- Develop a logistic regression churn model.
- Evaluate predictive performance on unseen test data.
- Interpret model coefficients using odds ratios.
- Identify customer characteristics associated with churn risk.

## Methodology

### 1. Data Preparation

The dataset is inspected for missing values, data types, class balance, and potential modelling issues.

Variables are prepared using a **tidymodels recipe**, ensuring that preprocessing steps are applied consistently to both training and future prediction data.

### 2. Stratified Train/Test Split

The dataset is divided into training and testing sets using **stratification on the churn outcome**.

This helps preserve the proportion of churned and non-churned customers across both datasets and reduces the risk of an unrepresentative test sample.

### 3. Preprocessing Recipe

A documented `recipes` workflow is used to prepare the predictors.

Depending on the dataset, preprocessing may include:

- Missing-value handling
- Removing irrelevant variables
- Encoding categorical variables
- Converting categorical predictors into model-ready features
- Normalising numerical predictors where appropriate

Keeping preprocessing inside the recipe helps prevent data leakage and makes the modelling workflow reproducible.

### 4. Cross-Validation

The training data is evaluated using **k-fold cross-validation**.

Cross-validation provides repeated estimates of model performance without using the final test set during model development.

### 5. Logistic Regression

A logistic regression model is used to estimate the probability that a customer will churn.

The model provides both:

- A predicted probability of churn
- An interpretable relationship between customer characteristics and churn

### 6. Odds Ratio Interpretation

Model coefficients are converted into **odds ratios** to make the results easier to interpret.

An odds ratio:

- **Greater than 1** indicates higher odds of churn.
- **Less than 1** indicates lower odds of churn.
- **Equal to 1** indicates little or no change in the odds.

This allows the analysis to move beyond prediction and provide explanations that can support customer-retention decisions.

## Analytical Workflow

```text
Customer Data
      ↓
Data Exploration & Cleaning
      ↓
Stratified Train/Test Split
      ↓
Preprocessing Recipe
      ↓
Cross-Validation
      ↓
Logistic Regression
      ↓
Model Evaluation
      ↓
Odds Ratio Interpretation
      ↓
Churn Risk Insights
      ↓
Quarto Report
```

## Technologies Used

- **R**
- `tidymodels`
- `dplyr`
- `ggplot2`
- `recipes`
- `parsnip`
- `workflows`
- `yardstick`
- `rsample`
- **Quarto**

## Model Evaluation

The model is evaluated using appropriate classification metrics, which may include:

- Accuracy
- Sensitivity
- Specificity
- ROC AUC
- Confusion matrix
- ROC curve

The final test set is kept separate from model development and provides an estimate of performance on unseen customer data.

## Project Structure

```text
customer-churn-prediction-r/
│
├── data/
│   └── customer_churn.csv
│
├── R/
│   ├── 01_data_preparation.R
│   ├── 02_train_test_split.R
│   ├── 03_preprocessing_recipe.R
│   ├── 04_cross_validation.R
│   ├── 05_logistic_regression.R
│   └── 06_model_evaluation.R
│
├── figures/
│   ├── churn_distribution.png
│   ├── roc_curve.png
│   └── odds_ratios.png
│
├── results/
│   ├── model_metrics.csv
│   └── odds_ratios.csv
│
├── report/
│   └── customer_churn_analysis.qmd
│
└── README.md
```

## Business Application

Customer churn prediction can help organisations identify customers who may be at risk of leaving.

The model can support:

- Customer retention campaigns
- Targeted offers
- Customer relationship management
- Resource prioritisation
- Churn-risk monitoring
- Data-driven retention strategies

The odds-ratio analysis also helps explain **which customer characteristics are associated with churn**, making the results more useful for business decision-making.

## Reproducibility

To reproduce the analysis:

1. Install R and the required packages.
2. Install Quarto.
3. Place the dataset in the `data/` directory.
4. Run the R scripts in the appropriate sequence.
5. Render `customer_churn_analysis.qmd`.
6. Review the generated tables, visualisations, model metrics, and interpretations.

## Skills Demonstrated

This project demonstrates practical skills in:

- R programming
- Machine learning
- Binary classification
- Logistic regression
- Customer churn modelling
- Tidymodels workflows
- Data preprocessing
- Stratified sampling
- Cross-validation
- Model evaluation
- Statistical interpretation
- Odds-ratio analysis
- Data visualisation
- Quarto reporting
- Reproducible analytics

## Conclusion

This project demonstrates an end-to-end approach to customer churn prediction, combining sound data-splitting practices, reproducible preprocessing, cross-validation, interpretable logistic regression, and business-focused model interpretation.

The resulting workflow provides both **predictive insight into which customers may churn and explanatory insight into factors associated with churn risk**.
