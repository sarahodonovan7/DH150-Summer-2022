# Machine Learning and Seoul Bike Data #

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/sarahodonovan7/DH150-Summer-2022/HEAD?urlpath=https%3A%2F%2Fgithub.com%2Fsarahodonovan7%2FDH150-Summer-2022%2Ftree%2Fmain%2FDH150%2520Project)

#### Background
The goal of this project is to perform various Machine Learning algorithms on a data set, and compare our findings with the work of prior researchers. In addition to attempting to achieve similar findings, we will also include new methods of data analysis. In an effort to recreate similar data to the prior existing work, we applied the Machine Learning Methods of Linear Regression, Decision Trees, and Random Forest.

The data set in question contains informationcollected over a one-year period, from December 1, 2017 to November 30, 2018. This data pertains to bike rentals in Seoul, South Korea, collecting the number of rentals per hour per day as well as a number of other features. 
The original data set can be found at the following link: https://archive.ics.uci.edu/ml/datasets/Seoul+Bike+Sharing+Demand
I was able to identify two main articles that have previously performed Machine Learning models on this data set. Both articles applied a number of Machine Learning methods applied to the dataset, many of them going beyond the scope of our class. The relevant papers are listed below:

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

###### no holiday=0, holiday=1
###### functional day=1, non functional day=0
###### winter=1, spring=2, summer=3, autumn=4
###### Jan=1, Feb=2,..., Dec=12 ####

These changes will allow for easier implementation of code to the data, following similar pre-analysis modifications as to the original researchers.

-----

#### Prior Work

In regards to the article entitled "Using data mining techniques for bike sharing demand prediction in metropolitan city," five statistical regression models were trained with the best hyperparameters using repeated cross-validation. For the sake of this project, we will focus primarily on the regression models of linear regression and boosted/decision trees. For Linear regression, the most linearly fitted variable for predicting the dependent variable is ordered and used as a measure to calculate the variable importance. The GBM model has the highest predictive outcomes in the test set. The linear regression model produces the worst results compared to other models. This shows that the usage count is not linearly related to any of the independent variables. Temperature and Hour are considered as the most significant variables for the hourly rental bike count prediction in all 
models except linear regression. Overall, the linear regression model does not allow for full connections between all of the parameters described, and provides less for data analysis and commonality detection than the other data methods.

In terms of limitations, there are some factors that may not affect whether or not the user needs to rent a bike. For example, in a large city like Seoul, biking might be the sole method of transportation for people whether its going to work or running errands. In some cities, bike rental programs are more economically sound than owning and storing a personal bike as it is too much hastle. That being said, some users would rent a bike regardless of the weather or season, therefore eliminating these factors as contributions to 
data. Also, distance travelled on bike should be another factor contributing to the number of bike rentals. Determing how far the rentl location is from the return location, as well as some sort of mileage tracker, may allow the researchers further insight into how impactful bike rentals are in Seoul. Whether rental is for commuting to work,running errands, or personal leisure would certainly play 
a factor in importance of accessible rentals.


For the article titled "A rule-based model for Seoul Bike sharing demand prediction using weather data," five different machine learning methods were also used to create data visualizations.
In order to create our own results relating to this article, Random forest (RF), classification and regression trees (CART), and K-nearest neighbors (KNN) are the methods used that we will analyze. The model which provides the highest R^2 values and lowest Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and Coefficient of Variance (CV) will be determined as the best model to use for further analysis and interpretation. The results of the original study determined that KNN has the worst performance compared to other prediction models. Since RF is an combination of multiple CART, the performance of RF is higher than CART. This proves that ensemble strategies applied on RF model makes it so it will ultimately perform better than CART. It was also determined that Hour and Temperature are the most influential variable for the Seoul Bike data, since these variables are ranked among top five most influential variables by all the predictive models developed. The researchers determined that this system of modeling can be further applied to individual districts, in order to extract more data.

In regards to limitations, the researchers determined that KNN was the worst model predicted and it did not provide much contribution 
to the analysis of the data results. However, the shortcomings of the results provided by KNN were counteracted by the use of other 
models. Similarly to the previous article, adding more features for analysis would provide a wider array of results to draw a 
conclusion from. This includes miles traveled, distance of return destination from rental destination, how many rentals does one user 
participate in per year, etc. All of these factors can reveal more information on the prevelance and importance of bike sharing, which 
would hopefully enact some of these resources to other cities all over.

give specifics: if the Random Forest model gave the best performance, followed by classification and regression trees and then by k-nearest neighbors, it would be useful to know what the metric was for assessing performance and how much they differed (i.e. something like “The accuracy of RF was found to be 97% when training on the 5 features most highly correlated with bike rental count, followed by 90% accuracy for CART and 83% accuracy for KNN”)

TALK ABOUT OVERLAP BETWEEN ARTICLES.

-----
#### comparre prior work to my work



-----
### Citations 
[1] Sathishkumar V E, Jangwoo Park, and Yongyun Cho. 'Using data mining techniques for bike sharing demand 
prediction in metropolitan city.' Computer Communications, Vol.153, pp.353-366, March, 2020.

[2] Sathishkumar V E and Yongyun Cho. 'A rule-based model for Seoul Bike sharing demand prediction using weather 
data' European Journal of Remote Sensing, pp. 1-18, Feb, 2020.