House Price Prediction
Project Overview

This project focuses on predicting residential house sale prices using a rich set of structural, locational, and condition-based features. The objective is not only to build an accurate regression model but also to understand which property attributes contribute most to sale price in the presence of a large number of features.

The analysis involves extensive data cleaning, feature engineering, and model comparison across linear and non-linear approaches.

Dataset Description

Rows: 2,930

Columns: 69

Target Variable: SalePrice

The dataset includes detailed information about:

Area and location: lot size, neighbourhood, zoning

House condition: overall quality, condition ratings

Structure: basement details, exterior materials, number of floors

Sale attributes: sale type and year

A detailed data dictionary was used throughout the project to ensure correct interpretation of feature definitions.

Data Quality and Preparation

24 columns contained missing values

The Alley feature, with approximately 93% missing values, was removed

Remaining missing values were handled using domain-informed imputation:

Numeric features were filled with 0 where missing values indicated the absence of a feature

Categorical features were filled with 'None' to explicitly represent missing categories

No duplicate records were found

All feature data types were validated for consistency

Exploratory Data Analysis (EDA)

Several numeric features exhibited heavy right skewness and were log-transformed

Outliers were identified and removed from key features such as Gr Liv Area, Overall Quality, and Garage Cars

Categorical variables were analysed using grouped statistics and boxplots

Categories with low representation or similar median sale prices were merged to reduce sparsity

Multicollinearity among numeric features was assessed using variance inflation factor (VIF) analysis, leading to the removal of redundant features

Feature Engineering

Binary categorical features were label-encoded

Nominal categorical features were one-hot encoded

Ordinal categorical features were mapped to ordered numerical scales

New features such as House Age and Remodel Age were derived from year-based variables

All numeric features were standardised to ensure comparable magnitudes

Feature relevance was assessed using correlation analysis, ANOVA, mutual information, and random forest–based feature importance

Features showing consistently weak importance were removed from the final model

Modelling Strategy

A baseline Linear Regression model was used to establish a benchmark

Elastic Net was applied to address correlated features and stabilise coefficients

An XGBoost Regressor was implemented to capture non-linear relationships and feature interactions

Cross-validation was used to assess model stability

SHAP values were used to evaluate global feature importance and validate model behaviour

Evaluation Framework

Model performance was evaluated using:

Root Mean Squared Error (RMSE)

R² score

The goal was to minimise prediction error while maximising explanatory power.

Model Performance

While the baseline linear regression model achieved strong RMSE and R² values, coefficient analysis revealed inflated dummy variable importance. Elastic Net improved regularisation but continued to exhibit similar behaviour. The XGBoost model achieved an RMSE of 0.11 and an R² value of 0.90, with feature importance rankings highlighting meaningful housing attributes rather than dummy variables. Cross-validation results confirmed stable performance on unseen data, supporting XGBoost as the final model.

Limitations

The model was trained on a relatively small sample of approximately 2,900 houses

A larger and more diverse dataset would provide a stronger assessment of generalisability

Disclaimer

This project is intended for educational and analytical purposes only and should not be used as a production-ready pricing system.
