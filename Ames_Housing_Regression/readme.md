# Ames Housing Data and Kaggle Challenge
Date: **May 18, 2018**

![alt text](https://github.com/jonmvail/JonVailPortfolio/blob/master/Ames_Housing_Regression/Images/Ames%20city.PNG)

## Goal
Create a regression model that can predict the price of houses in Ames Iowa with the data from the Kaggle page (https://www.kaggle.com/c/ames-housing-data) 


## Data

80 columns of features were provided including items like Suare feet of different rooms, neighborhoods, and number of certain amenaties (like fireplaces). 

## EDA

Many columns had a number of Null values. float columns had their nulls set to the mean of the columns. Many other columns with null values indicated that they value was zero as opposed to being missing, so these items were set as such. Outliers were found but allowed to remain for the modeling process.


## Modeling

**Model 1** 
*Cleaning and Basic Regression Workbook*
A basic linear regression was used only with numerical value to start. 
R-squared .65

**Model 2**
*Cleaning and Basic Regression Workbook*
A model using the numeric value features and creating PolyFeatures with them
R-squared .80

**Model 3**
*Selected Lin Regression*
I selected the features I felt would be most aplicable to a house based on my experience. I used both numerical and dummy features
R-squared .77

The top features are as follows
1) Neighborhood_GrnHill	
2) Year Remod/Add_2010
3) Neighborhood_StoneBr
4) Year Remod/Add_2009
5) MS Zoning_I (all)
6) Neighborhood_NoRidge
7) Neighborhood_Veenker
8) MS Zoning_FV
9) Neighborhood_NridgHt
10) MS Zoning_RL

**Model 4**
Used Lasso to select the features for me.
R-Squared .81

The top features are as follows
1) Gr Liv Area
2) Overall Qual_9	
3) Overall Qual_10	
4) BsmtFin SF 1	
5) Total Bsmt SF	
6) Overall Qual_8	
7) Lot Area	
8) Mas Vnr Area	
9) Garage Area	
10) Exter Qual_TA	

## Evaluation

Using Lasso for feature selection is more useful then selecting features on your own
