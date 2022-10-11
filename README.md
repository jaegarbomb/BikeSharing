# Bike Sharing Case Study
## Table of Contents
* [General Info](#general-information)
* [Business Goal](#business-goal)
* [Files](#files)
* [Libraries](#libraries)
* [Important Observations](#important-observations)
* [Conclusions](#conclusions)
* [Replication](#replication)

## General Information
A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

The business has shared their 2 year data from Jan 1,2018 to Dec 31st 2019 for us to analyse. The data contains weather details, temperature, humidity, and other details like if the date was a holiday or working day. Based on these factors, we are required to build a Linear Regression to predict their customer numbers.

## Business Goal:
You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 

## Files: 
- **day.csv** : the main data source
- **Bike_Sharing_Analysis.ipynb** : The final model created to predict the count of users.

## Libraries:
- Pandas
- Numpy
- Matplotlib and Seaborn
- statsmodels
- Scikit-learn

## Important Observations:
I noticed some of these observations during the analysis and modelling:

1. The test-set makes a significant difference in the modelling. I used a 80:20 ratio (**test_size =  0.2**) for training the model. Choosing other than this results in different features to be removed.
2. Seed was set at **42**.
3. The value **"yr"** has a massive effect on the model. Logically speaking, the value of *year* should have no difference on the model i.e. user demand, yet removing this causes the $R^{2}$ to fall from  ~0.84 to ~0.59. 
4. *atemp* or *temp* and *hum* showed a very High Variance Inflation factor (VIF). By logic, these should have been removed. Yet, when the variables are removed, the $R^2$ value fell from **0.84** to **0.58**. Thus it makes sense to keep these, as temperature and humidity are important factors for customer to decide whether they want to use a bike or not.

## Conclusions
- **Summer** and **Winter** are the seasons to focus on for business growth.
- **Humidity** and **windspeed** reduces decreases usage, thus having a weather forecast model to predict this is beneficial as we can reduce the operational costs during this time.
- **Months of July to Nov** sees the most use. This corresponds to the seasons of demand.
- **Working days** (with the exception of Tuesday) sees a high utilisation of bikes.
- **Weather Situation**: clear weather and mist sees high usage of bikes.

## Replication
To replicate the results in your local system, download the following files:
 - day.csv
 - Bike_Sharing_Analysis.ipynb