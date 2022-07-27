# Machine Learning and Seoul Bike Data #

#### Background
The goal of this project is to perform various Machine Learning algorithms on a data set, and compare our findings with the work of prior researchers. In addition to attempting to achieve similar findings, we will also include new methods of data analysis. INSERT TYPE OF ML HERE

In particular, we will analyze data collected over a one-year period, from December 1, 2017 to November 30, 2018. This data pertains to bike rentals and returns in Seoul, South Koeaa. 
The original data set can be found at the following link: https://archive.ics.uci.edu/ml/datasets/Seoul+Bike+Sharing+Demand

I was able to identify two main articles that have previously performed Machine Learning models on this data set. The relevant papers are listed below:

[1] Sathishkumar V E, Jangwoo Park, and Yongyun Cho. 'Using data mining techniques for bike sharing demand prediction in metropolitan city.' Computer Communications, Vol.153, pp.353-366, March, 2020.

[2] Sathishkumar V E and Yongyun Cho. 'A rule-based model for Seoul Bike sharing demand prediction using weather data' European Journal of Remote Sensing, pp. 1-18, Feb, 2020.

The data set itself includes a variety of features to better categorize the collected bike data. These features include the following:

###### Date : year-month-day
###### Rented Bike count - Number of bikes rented at each hour
###### Hour - Time of the day
###### Temperature - Celsius
###### Humidity - %
###### Windspeed - m/s
###### Visibility - 10m
###### Dew point temperature - Celsius
###### Solar radiation - MJ/m2
###### Rainfall - mm
###### Snowfall - cm
###### Seasons - Winter, Spring, Summer, Autumn
###### Holiday - Holiday/No holiday
###### Functional Day - Yes (Functioning Day), No (Non-functioning Day)

In order to prepare the file for easier Machine Learning applications, I made the following modifications to the seasons, holiday, functional day, and date features:
#
###### no holiday=0, holiday=1
###### functional day=1, non functional day=0
###### winter=1, spring=2, summer=3, autumn=4
###### Jan=1, Feb=2,..., Dec=12 ####

These changes will allow for easier implementation of code to the data, following similar pre-analysis modifications as to the original researchers.