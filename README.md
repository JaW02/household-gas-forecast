# Household Gas Usage Forecast & Optimisation App
## Introduction
No one likes the surprise of opening their latest energy bill to find that the cost is increasing because the latest energy readings show a rise in consumption. This all being a common scenario, but if we can leverage the data of our past gas consumption then we can gain the ability to stay on top of the amount of future gas we use (providing the non occurence of black swan events), therefore no nasty surprises in the post. Furthermore if we utilise the future gas forecast to enable us to apply a cost threshold to the amount of gas we consume, we can then have the ability to cut the costs and amount of gas we use bringing energy bills down and also doing our bit for the environment.

### Project Summary
With the above in mind the idea behind this project was to forecast future household gas consumption for central heating from previous household gas usage data, and create an optimisation app which utilises the usage pattern from the future forecast to provide the homeowner the ability to apply a cost threshold to their gas consumption in order to have more control and aid in keeping household energy bills down. We aimed to achieve future gas forecasts via the use of time series modelling and also converting the time series problem into a normal regression problem so that linear/non-linear and tree models could also be used, with the performance metric of choice being RMSE as the data showed no presence of outliers. We found using a simple model of best feature produced a baseline RMSE score of approx. 22 but using the monthly average gas consumption as a baseline produced a better RMSE score of approx. 18. The best performing model was a gradient boosting model that was trained on the converted time series data obtaining an RMSE score of approx. 15 with a difference of £2.68 between actual and forecast gas consumption.

## Dataset
The data were obtained online from kaggle and were in SQL format, the data provided household energy readings, exterior temperature and interior temperature readings from 2013 up until 2019 with a total of over 1.5 million readings. As the readings were recorded sequentially the singular readings (e.g. electricuty consumption, gas consumption, room temps, outside temp) were extracted in SQL to create seperate datasets of each reading source so that the correct data could be acquired, then using pandas the data were aggregated to average monthly temperature readings and total gas consumption bringing the data down to a total of 62 observations. The time series data consisted of the datetime feature as the index with the total monthy gas consumption as feature, for modelling the time series data as a regression problem lag features for gas consumption were engineered aswell as extracting month and year from the datetime feature also season, average outside temperature and the cyclical nature of season and month using their sin and cosine were initially included.

## Preprocessing
The data contained no missing values, errornous observations or duplicate observations, outliers were detected using the interquatile range and for the majority of the data no outliers were detected, outliers that were found belonged to redundant features and were consequently removed.

## Features // Feature Engineering
The types of features engineered in modelling as a regression problem were; average features, lag features, rolling means, expanding means, power features, k nearest neighbour local prediction, interaction features, ratio features, sin/cosine features.

## EDA

## Modelling

## Results

## Conclusion

## Future Improvements
