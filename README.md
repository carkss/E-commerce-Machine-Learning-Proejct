# E-commerce-Machine-Learning-Project

This project analyzes two ecommerce datasets found on Kaggle: global online transactions "https://www.kaggle.com/datasets/yusufdelikkaya/online-sales-dataset"  and Amazon UK market data "https://www.kaggle.com/datasets/asaniczka/amazon-uk-products-dataset-2023" . 

The main goals are:
- Applying unsupervised learning to segment customers
- Regression models to predict product ratings
- Classification techniques to identify consumer country of origin based on transaction details

All tasks aim to uncover consumer patterns, improve product insights, and enhance market targeting using various machine learning methods. While most importantly, developing familiarity with the full pipeline of building predictive models and  understanding what defines a good prediction through model evaluation.
This project contains extensive data wrangling and cleaning and implementation of various prediction algorithms for each techniques in only R. 

### NOTE: THE FOLLOWING OVERVIEW IS A BRIEF SUMMARY. FOR DETAILED DATA WRANGLING STEPS, REFER TO THE R CODE FILE. FOR A MORE STRUCTURED AND CONCISE EXPLANATION OF THE METHODOLOGY AND FINDINGS, PLEASE SEE THE WORD REPORT.

## Overview of data wrangling steps: 

For global online transaction dataset:
 1. Remove any irrelevant variables and rows with missing values
 2. Standarise Currency across all price related variables
 3. Conduct Exploratory Data Analysis ( EDA ) and from the visualisations determine which variables are insignificant or are too skewed to prevent biaseness
 4. Convert and encode categorical variables into numeric variables and do a final cleaning of unnesscary variables to prevent inaccuracies
 5. Apply unsupervised learning algorithms : Principal Component Analysis ( PCA ) , K-means clustering and Hierarchical clustering to determine optimal number of clusters 
 6. Implement Classification techniques: K Nearest Neighbour ( KNN ) and Logistic Regression and compare which model is better in prediciting consumer's country of origin

For Amazon UK market dataset:
 1. Remove any irrelevant variables and NaN values
 2. Modify the "categoryName" variable to scale down the dataset into 5 subcategories and exclude mismatch and low frequency inputs
 3. Standarise Currency across all price related variables
 4. Conduct EDA and remove any unreliable or uncorrelated variables
 5. Convert and encode any categorical variables into numeric
 6. Run Regression models: Linear Regression, Regularisation Models ( Lasso, Ridge and net ) and Random Forest to find how accurately regression model predict product's ratings and whether regularisation models help in improving predicition 

## Key insights: 
1. PC1 explains 13.39% of the total variation. The cumulative proportion indicates after PC4, 46.11% of the variation can be explained by the first 4 PCs. Overall, the PCA does reduce dimensions while retaining a good portion of the variance but the percentage could be higher.
2. The optimal number of clusters is 3
3. The 2 best performing models in Hierarchical clustering are Ward's Linkage in Manhattan Distance and Average Linkage in Euclidean Distance
4. KNN performs well in predicting the correct country and identifying the correct instances of the target class. However, the precision having 31% indicates a high number of wrongly identified countries. In addition, all the Country’s ROC curve are generally performing well.
5. In Logistic Regression, all the Country’s ROC curve are generally performing well as its higher than the benchmark but most countries are relatively flatter. Precision and recall values are relatively low which indicates high wrongly predicted countries. Overall for majority of the countries the better model is KNN
6. Some variables have a positive relationship with product ratings while others have an inverse relationship 
7. Adjusted R-square indicates that 41.89% of the variation can be explained by the model’s predictors which could be better. Since the F-statistic is large while the p- value is extremely small, we can conclude that the model is significant.
8. A residual plot done shows that most of the residuals are evenly distributed around the fitted values, indicating good fit of the model, however presence of possible non-linearity is also exhibitied
9. The 3 regularisation models don’t explain much variation due to the low R-squared and high RMSE. However, Ridge does slightly outperform the other 2 regression models. Overall they dont help improve predicitive power
10. Random Forest captures general trends in star ratings, but it has a tendency to overestimate low ratings and underestimate high ratings. Overall, while neither model is perfect, Random Forest appears to perform better than Linear Regression in capturing complexity. 
