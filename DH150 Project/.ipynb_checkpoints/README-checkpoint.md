# Machine Learning and Seoul Bike Data #

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/sarahodonovan7/DH150-Summer-2022/HEAD)

#### Background
The goal of this project is to perform various Machine Learning (ML) algorithms on a data set, and compare our findings with the work of prior researchers. In addition to attempting to achieve similar findings, we will also include new methods of data analysis. In an effort to recreate similar data to the prior existing work, we applied the Machine Learning Methods of Linear Regression, Decision Trees, and Random Forest.

The data set in question contains informationcollected over a one-year period, from December 1, 2017 to November 30, 2018. This data pertains to bike rentals in Seoul, South Korea, collecting the number of rentals per hour per day as well as a number of other features. 
The original data set can be found at the following link: https://archive.ics.uci.edu/ml/datasets/Seoul+Bike+Sharing+Demand
I was able to identify two main articles that have previously performed Machine Learning models on this data set. Both articles applied a number of Machine Learning methods applied to the dataset, many of them going beyond the scope of our class. That being said, I intend to focus on ML methods that are covered in our class. The relevant papers are listed below:

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

When attempting to analyze the unmodified data set, I found that it would be unnecessarily complicated to develop code to read the string inputs. However, neither article elaborated on what modication methods they took to address this issue as they gave no reference code or further explanation. In order to prepare the file for easier Machine Learning applications, I decided to manually modify the data set in its CSV file, and assign the string text to specific numerical values. I made the following modifications to the seasons, holiday, functional day, and date features:

###### no holiday=0, holiday=1
###### functional day=1, non functional day=0
###### winter=1, spring=2, summer=3, autumn=4
###### Jan=1, Feb=2,..., Dec=12 ####

For the date feature, rather than assign a value to each date in a month, I rather assigned one numerical value to the entire month's worth of data. I decided to do this under the assumption that there is no significant fluctuation in data from day to day per month, but that we would rather see more fluctuation comparing entire months to each other. These changes will allow for easier implementation of revelant code, and allowing us to follow an assumed similar pre-analysis modifications as to the original researchers.

-----

#### Prior Work

Both articles used three main statistical methods to determine accuracy and efficiency of the ML methods. Root mean squared error (RMSE), mean absolute error (MAE), and Rsquared (R2) are all important statistical calculations that provide further insight on the quality of data visualizations. 

In regards to the first article, entitled "Using data mining techniques for bike sharing demand prediction in metropolitan city," five statistical regression models were trained with what was determined to be the best hyperparameters using repeated cross-validation. For the scooe of this project, we will focus primarily on the results of their Linear Regression model (LM). For Linear regression, the most linearly fitted variable for modeling the dependent variable is trained and then used as a measure to calculate the variable importance. After doing so, it was determined that LM produces the worst results compared to other models. The RMSE and MAE values were very high, and the R2 value was low; all three of these combine to give a bad statistical model. This shows that the usage count cannot be determined as linearly related to any of the independent variables. For all models except LM, outside temperature and hour of rental are considered as the most significant variables for the rental bike count prediction. However, hour of rental is the only factor that they determined to contribute to the LM of rental bike count. Overall, the linear regression model does not allow for full connections between all of the parameters described, and provides less for data analysis and commonality detection than the other data methods.


For the article titled "A rule-based model for Seoul Bike sharing demand prediction using weather data,"  five different machine learning methods were also used to create data visualizations. However, this second article did not overlap in any ML methods with the first article aforementioned. So for this section, we will analyze two of the methods used in the second article: regularized random forest (RRF) and classification and regression trees (CART). In order to create our own results relating to this article, decision tree regression models and random forest regression models were formed. The model which provides the highest R2 values as well as the lowest RMSE and MAE values will be determined as the best model to use for further analysis and interpretation. While we did not replicate a K-nearest neighbors (KNN) analysis, the results of the original study determined that KNN has the worst performance compared to other prediction models. According to the article, both RF and CART methods performed exceptionally well, with high R2 values and low RMSE and MAE values. Since RRF is an combination of multiple CART iterations, the performance of RRF is higher than CART. This proves that ensemble strategies applied on RRF model makes it so it will ultimately perform better than CART. As concluded in the first article, it was also determined here that hour of rental and outside temperature are the most influential variable for the Seoul Bike data. The researchers determined that this system of modeling can be further applied to individual districts within Korea, in order to extract more data and expand analysis.

As both articles analyzed the same set of data, they had many overlapping limitations within their results. In terms of limitations, there are some factors that may not affect whether or not the user needs to rent a bike. In a large city like Seoul, biking might be the sole method of transportation for people if they are frequently going to work or running errands. In many major cities, bike rental programs are more economically sound than owning a personal bike due to small living spaces and a lack of bike racks for storage. That being said, some users may rent a bike regardless of the weather or season if it is there only mode of transport. If true, this would render these factors obsolete. 
In order to narrow the accuracy of the machine learning applications, adding more features to the data set would be beneficial. Distance travelled on bike could be an important factor contributing to the number of bike rentals per person. If the distance between the rental location and the return location were to be calculated, it may give insight into what bike rentals are used for. An alternative to this could be the addition of a mileage tracker on the bikes. Whether renting a bike is essential for a daily commute to work, a biweekly errands, or infrequent personal leisure, noting these habits would give insight into the importance of accessible rentals. All of these factors can reveal more information on the prevelance and importance of bike sharing, which would hopefully encourage officials and planners of other cities to implement similar programs.

I also believe there is a level of inequality in regards to who may partake in city-wide bike rentals.


-----
#### Comparing Trained Model with Prior Work

When attempting to reproduce similar findings as to those in article one, I decided to perform a linear regression model on a cross-validated testing and training set. The results of this self-produced model are shown in Figure 1, alongside the results from the first article shown in Figure 2.

![Screenshot](Linear Regression Graph.png)


-----
### Citations 
[1] Sathishkumar V E, Jangwoo Park, and Yongyun Cho. 'Using data mining techniques for bike sharing demand 
prediction in metropolitan city.' Computer Communications, Vol.153, pp.353-366, March, 2020.

[2] Sathishkumar V E and Yongyun Cho. 'A rule-based model for Seoul Bike sharing demand prediction using weather 
data' European Journal of Remote Sensing, pp. 1-18, Feb, 2020.