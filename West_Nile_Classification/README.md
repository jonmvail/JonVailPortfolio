# Westnileproject4

Date: **June 15, 2018**

Jon Vail, Connor Foley, Tarin Poddar

## Goal
We preformed an analysis on the West Nile virus in Chicago and how best to predict the times inwhich the virus would be most likly to spread. 

## Data
We used data from the Kaggle compitition that included Weather, Trap, and Spray data. The weather data contained daily information from 2 stations in chicago. Trap data contained the location of traps around the city and when they were inspected. The number, species, and if the west nile virus was present was recorded. The Spray data contained information on when and where the city sprayed for mosquitos.

## EDA and Feature Engineering
The data needed to be cleaned, especially the weather data. Much of the information from station 2 was missing and many columns were not useful for analysis and were dropped. The training data needed to have the rows merged on Dat, Trap, and Species as the mosquito count would not go higher than 50 and then would go to a new row. After cleaning, the weather data was merged with the trap data. Merging spray data was attempted, but because the test data would not have any spraying, this was not deemed as essential and would be evaluated only if time permitted.
**(This code can be found in the clean merge Workbook)**

During EDA, we discovered many trends about when the peak West Nile season was for the city of Chicago. It is volitile for year to year, but seemed to be highest during rather wet summer months. In feature engineering, We created the following features.

## Day length
- Used sunrise and sunset to create a numerical variable

## Wind Direction Dummies
- Made ranges from 360 degrees data that gives direction of wind in 4 categories 

## Time
- Converted time to UTC float format.
 
## Weather Code dummies
- Found top occuring weather codes and created dummies for those instances 

## Temperature
- Used Tmax and Tmin to create a temperature range feature.


## Modeling
For modeling, we wanted to focus on models that could work best with Imbalanced classed. We tried many, but the one that worked best for us was a random forest that fed into a Balanced Bagging Classifier pipeline. This was used try and rebalance the classes. Through this we found that the most important features revoled around the Culex Species of mosquitos and the wetness of the weather. Unfortunatly, while we were about to get decent results when cross valitating with our own data, we were never able to get far past baseline with the kaggle data.
**(This code can be found in the Project4_Clean, Modeling create new target, and modeling SMOTE with adaboosting workbooks)**

## Findings
Our recomendations are to spray in the late July August time frame and after rains that would cause puddles that mosquitos could trive in. Also, if traps show a large amount of Culex mosquitos, spray in those areas as well. An evaluation of trap stations can be done as well to see if these stations need to be operating since they might be redundant and not in good locations as there have never been any detections of West Nile.

## Next Steps
For next steps, we would like to preform an analysis using time lagged data that would be more representative of the real world. We would also like to performa analysis on the spraying and how long the spray is effective for. 
