![Cannabis Market Forecaster](https://github.com/danielfrees/Cannabis_Market_Forecaster/blob/573fd2106d034a8e09f25c78437c67de5e509972/imgs/Project_Banner.png)

![GitHub last commit](https://img.shields.io/github/last-commit/danielfrees/Cannabis_Market_Forecaster?style=plastic)

Project Co-Created with Andrew Bennecke for CS 148 Final Project

## Find our full research report in Cannabis_BF_Report. 

## All model development and detailed results are contained in Cookies_ML_Proj.ipynb.

# Executive Summary: 

The cannabis market has seen record growth over the past few years and is projected to continue this growth throughout the decade. One key way that other industries have optimized their growth over the past several years has been through predictive and analytical machine learning models. The cannabis market is no exception to this practice and stands to accelerate its already rapid growth by exploring the vast quantities of pre-existing data relating to their industry. In this report, we explore a subset of this vast data and extract actionable insights.

First, several time-series and brand-level features were augmented in order to enhance the scope of the model. Several of the time series features include past sales data, rolling averages of units moved, brand market share, and brand length in market. Several of the brand-level features include product categorizations such as whether brands sell THC-containing products, and whether brands sell ingestible cannabis products. We then dropped all features with a high collinearity to the target feature Total Sales ($) because one of our primary goals was to identify uncommon features which may be strong predictors of Total Sales ($).

Once the data was cleaned, augmented, and imputed, 3 different models were explored. The first was a basic Linear Regression Model. The latter 2 methods employed an ensemble approach. The first of these was eXtreme Gradient Boosting Regression (XGB) and the second of these was Random Forest Regression (RFR). The hyperparameters of the XGB model was optimized using GridSearchCV, and the RFR model was selected and tuned via manual exploration. After identifying optimal sets of hyperparameters, each model was trained, tested, and K-fold cross-validated. To extract insights, confidence intervals were generated for linear regression coefficients, and cross-validated feature importances were generated for the ensemble models.

Cross-Validated Results: Model performance was extremely poor for the linear regression model (R2=0.2639, MAE/μ(sales)=0.9996). The XGB model was great at explaining variance in Total Sales ($), but still not particularly precise (R2=0.8897, MAE/μ(sales)=0.4437). The RFR model was the best at explaining variance in Total Sales ($), and was the most precise (R2=0.8961, MAE/μ(sales)=0.3695). 

Since model performance was so low for linear regression, inferences were made based on the XGB and RFR models, combined with Pearson’s correlation coefficients between features and Total Sales ($). The most significant positive predictor was NumProducts, indicating that some combination of product variety and brand size is a powerful indicator of Total Sales ($). Average retail price and recent market share growth were also consistently important predictors, suggesting that retail pricing and brand momentum are important factors driving monthly sales. 

In conclusion, Total Sales ($) for future months of cannabis sales can be predicted with moderate accuracy even after removing previous month sales and other highly correlated features. Upon generating models without these features, numerous avenues for further brand research become obvious. 
