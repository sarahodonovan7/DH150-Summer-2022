# Machine Learning and Seoul Bike Data 
### Sarah O'Donovan
#### DH150, 27th of July, 2022

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/sarahodonovan7/DH150-Summer-2022/HEAD?labpath=DH150%20Project)

#### Background
The goal of this project is to perform various Machine Learning (ML) algorithms on a data set, and compare our findings with the work of prior researchers. In an effort to recreate similar data to the prior existing work, we applied the machine learning methods of linear regression, decision trees, and random forest.

The data set in question contains information collected over a one-year period, from December 1, 2017 to November 30, 2018. This data pertains to bike rentals in Seoul, South Korea, collecting the number of rentals per hour per day as well as a number of other features. 
The original data set can be found at the following link: https://archive.ics.uci.edu/ml/datasets/Seoul+Bike+Sharing+Demand
I was able to identify two main articles that have previously performed machine learning models on this data set. Both articles applied a number of machine learning methods applied to the dataset, many of them going beyond the scope of our class. That being said, I intend to focus on ML methods that are covered in our class. The relevant papers are listed below:

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

When attempting to analyze the unmodified data set, I found that it would be unnecessarily complicated to develop code to read the string inputs. However neither article elaborated on what modication methods they took to address this issue, as they gave no reference code or further explanation. In order to prepare the file for easier machine learning applications, I decided to manually modify the data set in its CSV file, and assign the string text to specific numerical values. I made the following modifications to the seasons, holiday, functional day, and date features:

###### no holiday=0, holiday=1
###### functional day=1, non functional day=0
###### winter=1, spring=2, summer=3, autumn=4
###### Jan=1, Feb=2,..., Dec=12 ####

For the date feature, rather than assign a value to each date in a month, I rather assigned one numerical value to the entire month's worth of data. I decided to do this under the assumption that there is no significant fluctuation in data from day to day per month, but that we would rather see more fluctuation comparing entire months to each other. These changes will allow for easier implementation of revelant code, and allowing us to follow an assumed similar pre-analysis modifications as to the original researchers.

-----

#### Prior Work

Both articles used three main statistical methods to determine accuracy and efficiency of the ML methods. Root mean squared error (RMSE), mean absolute error (MAE), and Rsquared (R2) are all important statistical calculations that provide further insight on the quality of ML methods. 

In regards to the first article, entitled "Using data mining techniques for bike sharing demand prediction in metropolitan city," five statistical regression models were trained with what was determined to be the best hyperparameters using repeated cross-validation. For the scope of this project, we will focus primarily on the results of the Linear Regression model (LM). For Linear regression, the most linearly fitted variable for modeling the dependent variable is trained and then used as a measure to calculate the variable importance. After doing so, it was determined that LM produces the worst results compared to other models. The RMSE and MAE values were very high, and the R2 value was low; all three of these combine to give a bad statistical model. This shows that the rental count cannot be determined as linearly related to any of the independent variables. For all models except LM, outside temperature and hour of rental are considered as the most significant variables for the rental bike count prediction. However, hour of rental is the only factor that they determined to contribute to the LM of rental bike count. Overall, the linear regression model does not allow for full connections between all of the parameters described, and provides less for data analysis and commonality detection than the other data methods.


For the article titled "A rule-based model for Seoul Bike sharing demand prediction using weather data,"  five different machine learning methods were also used to create data visualizations. However, this second article did not overlap in any ML methods with the first article aforementioned. So for this section, we will analyze two of the methods used in the second article: regularized random forest (RRF) and classification and regression trees (CART). In order to create our own results relating to this article, decision tree regression models and random forest regression models were formed. The model which provides the highest R2 values as well as the lowest RMSE and MAE values will be determined as the best model to use for further analysis and interpretation. While we did not replicate a K-nearest neighbors (KNN) analysis in our own date, the results of the original study determined that KNN has the worst performance compared to other prediction models. According to the article, both RF and CART methods performed exceptionally well, with high R2 values and low RMSE and MAE values. Since RRF is an combination of multiple CART iterations, the performance of RRF is higher than CART. This proves that ensemble strategies applied on RRF model makes it so it will ultimately perform better than CART. As concluded in the first article, it was also determined here that hour of rental and outside temperature are the most influential variable for the Seoul Bike data. The researchers determined that this system of modeling can be further applied to individual districts within Korea, in order to extract more data and expand analysis.

As both articles analyzed the same set of data, they had many overlapping limitations within their results. In terms of limitations, there are some factors that may not affect whether or not the user needs to rent a bike. In a large city like Seoul, biking might be the sole method of transportation for people if they are frequently going to work or running errands. In many major cities, bike rental programs are more economically sound than owning a personal bike due to small living spaces and a lack of bike racks for storage. That being said, some users may rent a bike regardless of the weather or season if it is there only mode of transport. If true, this would render these factors obsolete. 
In order to narrow the accuracy of the machine learning applications, adding more features to the data set would be beneficial. Distance travelled on bike could be an important factor contributing to the number of bike rentals per person. If the distance between the rental location and the return location were to be calculated, it may give insight into what bike rentals are used for. An alternative to this could be the addition of a mileage tracker on the bikes. Whether renting a bike is essential for a daily commute to work, a biweekly errands, or infrequent personal leisure, noting these habits would give insight into the importance of accessible rentals. All of these factors can reveal more information on the prevelance and importance of bike sharing, which would hopefully encourage officials and planners of other cities to implement similar programs.

I also believe there is a level of inequality in regards to who may partake in city-wide bike rentals.


-----
#### Comparing the Trained Model with Prior Work

Below is a Google Docs link containing all of the figures that will be referenced in the following section:
https://docs.google.com/document/d/1Ov5z6nmUPHGVOImwmRQMOj2zeNRcYjCK0k_Pg2ujrII/edit?usp=sharing
When attempting to reproduce similar findings as to those in Article 1, I decided to perform a linear regression model on a cross-validated testing and training set. The results of this self-produced model are shown in Figure 1, alongside the results from the first article shown in Figure 2. In agreeance with the results found in Article 1, I found that the linear regression model had very poor results in comparison to the other models that were generated. The RMSE was calculated as 433.22, the MAE as 321.87, and the R2 value as 0.5446. These results mean that there is not an acurrately linearly fitted variable to model the remaining dependent variables for training. That being said, we can confirm that using an LM would not be an ideal method of Machine Learning in regards to the amount of bikes rented in Seoul.

When reproducing similar findings to those found in Article 2, I also found that Decision Tree and Random Forest Regression Models provided very precise results. For the decision tree models, similar to the CART modeling conducted in the second article, I found that increasing the max depth from 1, then to 3, and then to 12 showed a stable decrease in the RMSE and MAE values as well as an increase in the R2 value. This is a positive result, and something that further shows us we have good results. As shown in Figure 3, having a large max depth of 12 allows for the data to closely fit the residual line. The values of RMSE, MAE, and R2 at a max depth of 12 were 211.53, 111.23, and 0.8914, respectively.

For my reproduction of the random forest regression model, similar to RRF of Article 2, I found that increasing the max depth from 2 to 5 to 15 similarly increased the R2 value and decreased the RMSE and MAE values. As shown in Figure 4, a max depth of 15 produces results following closely to the residual line. The respective values of RMSE, MAE, and R2 for this max depth are 226.08, 127.32, and 0.876.


Overall, my attempts at reproducing similar results to the two articles were in fact successful, despite my not replicating every ML method used. The only difference is that while I anticipated the random forest model to be more accurate than the decision tree mode, I found the opposite to be true. However, this was only proven by a small margin of about 0.015 in the R2 value, so this may be deemed insignificant or hard to determine with certainty. While I did not attempt to replicate these results, both articles determined that both the hour of day and the outside temperature were the most significant contributors to the number of bikes rented per day in Seoul.

#### Final Remarks

After completing the analysis of the Machine Learning methods applied to the data set pertaining to Seoul Bike Rentals, I am not surprised at some of the results. I assumed that a linearly fitted model would be too generic and vague to account for all of the variables that go into a bike rental. A linear model is not great at catching outliers in a multivariable setting, so it would be hard to create a train and test data that closely aligned with the residual line generated. 

Since both decision trees and random forest machine learning methods have the option of increasing depth, it is no surprise that these methods produced the most accurate results. These ML methods were able to account for a larger amount of the features provided, which ultimately lead to a closer fit in data when the max depth of the decision tree was increased to 12 and the max depth for the random forest to 15. Having a larger depth means more data points being taken into account, and a larger sample size proves more accurate conclusions.

In regards to the results produced in the original articles, it is not surprising to me that both time of day and outside temperature affect the number of bikes rented per day. Even in Los Angeles, I am more likely to rent a bike down in Santa Monica on a hot summer weekend than on a cold and rainy Wednesday. If you assume that at least half of bike rentals consist of tourist rentals or other leisure purposes, these individuals would be most impacted by the time and the weather, decreasing the amount of rentals. 

I also feel as if there are major inequalities when it comes to bike rentals in a major city. For one, bikes are not accessible methods of transportation for the elderly or the disabled. This eliminates a large demographic of potential users, and requires the need for other functional methods of transportation. Luckily, Seoul also has accessible public transit. However, I cannot say the same about many major American cities, such as Los Angeles or large suburban areas. Overall, the implementations of city-wide programs such as bike rentals would have a positive impact on the community and should be something that more governments should consider in urban planning and development. 

-----
#### Citations 
[1] Sathishkumar V E, Jangwoo Park, and Yongyun Cho. 'Using data mining techniques for bike sharing demand 
prediction in metropolitan city.' Computer Communications, Vol.153, pp.353-366, March, 2020.

[2] Sathishkumar V E and Yongyun Cho. 'A rule-based model for Seoul Bike sharing demand prediction using weather 
data' European Journal of Remote Sensing, pp. 1-18, Feb, 2020.