# Ames Housing Sale Price Analysis

## Project Overview

This project examines the relationship between several housing characteristics and residential sale prices using the Ames Housing dataset.

The analysis focuses on whether Overall Quality, Above-Ground Living Area, Total Basement Square Footage, Garage Capacity, and Year Built are associated with differences in log-transformed sale prices.

The primary statistical method used is multiple linear regression.

## Dataset

The analysis uses a preprocessed version of the Ames Housing dataset obtained from Kaggle.

Dataset source: [AmesHousing Engineered Dataset on Kaggle](https://www.kaggle.com/datasets/saeedomranpour/ameshousing-engineered)

The Kaggle source describes a preprocessing pipeline that included missing-value handling, encoding, feature engineering, skewness transformations, outlier removal, correlation filtering, and scaling.

The original `SalePrice` variable was not present in the file used for this project, while `Log_SalePrice` was provided as the target variable. Several predictors also appeared in scaled form.

This analysis focuses on Overall Quality, Above-Ground Living Area, Total Basement Square Footage, Garage Capacity, and Year Built.

### Variables used

* `Log_SalePrice` — log-transformed sale price
* `Overall_Qual` — overall quality rating
* `Gr_Liv_Area` — above-ground living area
* `Total_Bsmt_SF` — total basement square footage
* `Garage_Cars` — garage capacity
* `Year_Built` — year the home was built

Overall Quality and Garage Capacity were treated as categorical variables in the final regression model.

## Methods

The analysis includes:

* Exploratory data analysis
* Correlation analysis
* Scatterplots
* Multiple linear regression
* Comparison of numeric and categorical model specifications
* ANOVA and Wald tests
* Model selection using AIC
* Residual diagnostics
* Multicollinearity assessment using VIF
* Influence diagnostics using leverage, Cook's distance, and studentized residuals
* Sensitivity analysis for influential observations

## Main Findings

Overall Quality showed a strong association with sale price, with lower quality ratings generally corresponding to lower predicted sale prices relative to the highest-quality homes.

Above-Ground Living Area and Total Basement Square Footage were positively associated with predicted sale price after accounting for the other variables in the model.

Garage Capacity and Year Built also provided additional information about differences in sale prices.

Treating Overall Quality and Garage Capacity as categorical variables produced a better-fitting model than treating them as continuous numeric predictors.

Diagnostic analysis identified mild heteroscedasticity and several influential observations, but sensitivity analyses suggested that the main coefficient estimates were generally stable.

## Repository Structure

```text
Ames_Housing_Sale_Price_Analysis/
│
├── Ames_Housing_Sale_Price_Analysis.Rproj
├── Ames_Housing_Sale_Price_Analysis.Rmd
├── README.md
│
└── Data/
    └── AmesHousing_engineered.csv
```

## Running the Analysis

1. Download or clone this repository.
2. Open `Ames_Housing_Sale_Price_Analysis.Rproj` in RStudio.
3. Open `Ames_Housing_Sale_Price_Analysis.Rmd`.
4. Install any required R packages.
5. Knit the R Markdown file to reproduce the analysis.

The project uses relative file paths so the analysis can be reproduced without modifying computer-specific directory paths.

## Limitations

This analysis is observational and therefore does not establish causal relationships between housing characteristics and sale prices.

The final model also showed mild heteroscedasticity, and some factor levels contained relatively few observations.

Potential spatial or temporal dependence among housing transactions was not explicitly modeled.

## Tools

* R
* R Markdown
* Multiple Linear Regression
* `car`
* `dplyr`
* Base R statistical and diagnostic functions
