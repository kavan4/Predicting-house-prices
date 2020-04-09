# Problem Statement
This project comes up with a tool for realtors and homeowners to help predict the price of a new house listed in Ames,IA and provides recommendations for housing features that directly affect sale price.



# Executive Summary

### Data Import & Cleaning
Before plotting and making any statements, the data needed to be cleaned up.

### Exploratory Data Analysis
Identifying outliers, errors, and cleaning Null & blank values.

### Encoding
Encoding the Qualitative variables.
The ordinal variables have been ordinally encoded and the nominal variables have been dummy encoded.

### Feature Engineering
Each individual house feature's correlation to Sale Price was calculated.
Analyzing the features, distributions, and their correlations, the most significant ones were combined linearly and polynomially (degree=2) to improve the performances of the model.  

### Modelling
Linear Regression, Lasso Regression, and Ridge Regression were modelled on the given data.
A list of values for the hyperparameter lambda (alpha for sklearn) were calculated to find the one giving the best performance.



# Data Dictionary

Link to Data Dictionary: http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

Data Dictionary for some of the combined features. The others are identifiable as the name as ^2 to indicate squaring and names of features listed out to indicate multiplication.

|Combined Feature| |Feature1|Feature2|Feature3|Feature4|
|---|---|---|---|---|---|
|New_Gar_Feat| |Garage Area|Garage Qual|Garage Cond| |
|New_Bsmt_Feat| |Total Bsmt SF|Bsmt Cond|Bsmt Qual| |
|New_Ovr_Kit_Feat| |Gr Liv Area|Overall Qual|Overall Cond| Kitchen Qual|

Additional features can be analyzed to combine to improve the performance of the model.



# Conclusions and Recommendations

### Conclusions

The three models have very similar performances with all their respective scores being in the lower 90% range for the test set.
The models also had a very similar test and train set scores indicating that there was no over-fitting. The difference is scores was under 5 points and not significant enough to indicate under-fitting. Any of the models could be used for predicting the price.

The highest score was for Ridge regression @0.90038 without polynomial features
With polynomial features, Ridge regression still has the highest score @0.936041286135239

### Recommendations

Non poly - All models seem to be prioritizing the feature Overall Qual, Gr Liv Area, BasmtFin SF1, and 1st Flr SF the most. The Overall quality of the home seems to be the best indicator.To get even better performance, one might consider creating polynomial features by combining this with some other features if time permits.

Poly - All models seem to be prioritizing the feature New_Bsmt_Feat New_Ovr_Kit_Feat the most. This is a polynomial feature which in turn was created by a combination of features of other features. This makes sense as this features cover the polynomial combination of: Total Bsmt SF, Bsmt Qual, Bsmt Cond, Overall Qual, Overall Cond, Kitchen Qual, and Gr Liv Area The subsequent features seem to differ in priority based on model.

Paying close attention to these features and improving quality where possible can have a direct affect on the Sale Price.
