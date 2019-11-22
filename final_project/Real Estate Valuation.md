# Real Estate Valuation

**Kun Huang, Yizhou Jin, group 6**



We aim to predict the house price `house_preic` in New Taipei City, Taiwan using a data set containing the following variables,

- `trans_date`: the transaction date (for example, 2013.250=2013 March, 2013.500=2013 June, etc.)
- `house_age`: the house age (unit: year)
- `distance_mrt`: the distance to the nearest MRT station (unit: meter)
- `stores`: the number of convenience stores in the living circle on foot (integer)
- `latitude`: the geographic coordinate, latitude. (unit: degree)
- `longitude`: the geographic coordinate, longitude. (unit: degree)

The response variable is `house_preice`, the house price of unit area (10000 New Taiwan Dollar/Ping, where Ping is a local unit, 1 Ping = 3.3 meter squared).

The original contest can be see [here](https://www.scriptedin.com/contests/view/24).

## Preprocessing and Exploratory data analysis

Since directly using the geographic coordinates as predictor variables will lead some problems, we transform the longitude and latitude into a categorical variable ,`CENTROID_ID` to indicate the location of each observation. 

After looking at the map, we roughly observed that there are 4 clusters in the map, hence we decided to cluster longitude and latitude based on data features into 4 groups by using K-means clustering. This step is imposed on the whole data set, i.e., the training set and test set.

![newplot](D:\onedrive\classes\math5671\project\newplot.png)

Besides, we decided to exclude predictor `trans_date`before building the model since based on the following figure, we can see the season of transaction dates had relatively small influence on the house price.

![](D:\onedrive\classes\math5671\project\transdate.png)



By using the K-means model, we successfully cluster the latitudes and longitudes into four groups as follows.

![image-20191122173935399](C:\Users\41781\AppData\Roaming\Typora\typora-user-images\image-20191122173935399.png)

Then we subset the result table by train group and test group and we used `CENTROID_ID`, `house_age`, `distance_mrt`,  and `stores` as the predictors and `house_price` as the response variable to train the model and do the prediction.



## Model

We build a linear regression model using the BigQuery ML. Then we run the regression model and we use trained model to predict house price based on test data. The result is showed as follows.

![image-20191122174426060](C:\Users\41781\AppData\Roaming\Typora\typora-user-images\image-20191122174426060.png)

By submitting the data to Scriptedin, the score(MSE) is 13.1672 which is relatively good for a small dataset with size of 414.

![image-20191122174445801](C:\Users\41781\AppData\Roaming\Typora\typora-user-images\image-20191122174445801.png)