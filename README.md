# Multiple Linear Regression Bike Sharing Assignment


BoomBikes a US bike-sharing company has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state.



## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)


## General Information

The BoomBikes company wants to know:

1. Which variables are significant in predicting the demand for shared bikes.
2. How well those variables describe the bike demands

The following steps are to be followed in order to build a Multiple Linear Regression model to predict the demand for bike rentals

Step 1: Reading, Understanding and Validating the Data
Step 2: Data Visualisation for continuous and categorical variables
Step 3: Data Preparation for the model
Step 4: Spliting the Training and Testing data and analysing the multi-collinearity.
Step 5: Model building with all features
Step 6: Backward Elimination and finding the best features
Step 7: Verify the selected features with Recursive feature elimination
Step 8: Residual Analysis on the trained model
Step 9: Final model building and prediction
Step 10: Model Evaluation

At every step there were the following inferences

Step 1: Inference
The following observations are made on the features of the data

cnt is the output feature i.e., the demand and the sum of casual and registered is equal to count, hence those two columns can be ignored
The columns temp, atemp, hum, windspeed are the continuous input feature
The columns season, yr, mnth, holiday, weekday, workingday, weathersit are categorical input features
The column instant is a row number column which is of no use.
There was inconsistency in the features season, holiday, weekday, workingday, they were fixed
Based on these observations instant, casual and registered are dropped at the initial level and the columns with inconsistency were corrected.

Step 2: Inference
Based on the visualization it is evident that there lies a linear relationship between the atemp and cnt, and there was a high demand for bike rentals during the year 2019, when compared to that of 2018.

Step 3: Inference
The field dtday is not significant for model building, Hence it is dropped
The field holiday is a redundant since, the workingday is a combination of holiday and weekends
The following fields created for understanding the data were removed : 'year', 'day','season_map', 'month_map', 'holiday_map','workingday_map','weathersit_map'

Step 4: Inference
The fields temp & atemp are highly correlated, Let us decide if to keep the feature or not while model building.
The next feature to be considered for model building are atemp and yr

Step 5: Inference
From the above table it is evident that the VIF is high for temp and atemp, making it evident that out inference at Step 4 is valid. Hence it is recommended to consider removal of one feature.

Step 6: Inference
By doing the backward elimination it is evident that the features temp, weekday are insignificant for model building, because the Adjusted R square has no greater change while these fields were removed.

Step 7: Inference
The RFE analysis supports our previous findings that the fields weekday is insignificant.

Step 8: Inference
The Error terms are normally distributed to the mean, hence we are good with the linear model with the training dataset

Step 9: Inference
The final Linear model is built and the predictions are made on the y_test data set

Step 10: Inference
From the R squared values it is evident that the values of training and test R squares are 0.79 and 0.75 respectively.

## Conclusions

From all the steps performed in building the Multi Linear Regression model, it is evident that the features 'season', 'yr', 'mnth', 'workingday', 'weathersit', 'atemp', 'hum', 'windspeed' play a major role in forecasting the demand of bikes for rental. Also there were insignificant features like 'temp', 'weekday'.

## Technologies / Library Used

- Pandas 1.3.4
- Numpy 1.20.3
- Matplotlib 3.4.3
- Seaborn 0.11.2
- Holidays 0.13
- Datetime 4.4
- Statsmodel 1.16.0
- Sklearn 0.24.2



## License

Use of this dataset in publications must be cited to the following publication:

[1] Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, doi:10.1007/s13748-013-0040-3.

@article{
	year={2013},
	issn={2192-6352},
	journal={Progress in Artificial Intelligence},
	doi={10.1007/s13748-013-0040-3},
	title={Event labeling combining ensemble detectors and background knowledge},
	url={http://dx.doi.org/10.1007/s13748-013-0040-3},
	publisher={Springer Berlin Heidelberg},
	keywords={Event labeling; Event detection; Ensemble learning; Background knowledge},
	author={Fanaee-T, Hadi and Gama, Joao},
	pages={1-15}
}


##Contact

	
For further information about this dataset please contact Hadi Fanaee-T (hadi.fanaee@fe.up.pt)
