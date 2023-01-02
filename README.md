# Stock-Inventory-Prediction
Predict the quantity of inventory of goods that should be stocked by an e commerce company based on the quantity of orders that they are expected to process
# Project Goal
The goal is to predict the quantity of the products to be stocked for sale by a store that serves several countries from a common stock inventory. The prediction of the goods and quantities to be stocked are  for the month of November, 2011, using sales data spanning from December,2009 to October 2011. The outcome of the excercise shall be prediction file that contains the StockCode, the Product description and the corresponding Quantity of the products for the month of November.
# Approach
## The time series approach
In this approach, the problem is treated as a typical time series project and the time column is engineered to generate several new features that will aid in predicting the value of "y". In this approach, only the "Time" data is considered important in predicting the target, "y". Every other column is dropped and the Product codes role is simply for data labelling. It would not contribute to the algorithm for the actual predictions, It's only use is to be merged with the data  afterwards in order to enhance the usability and explainability of the generated predictions.
In addition to typical date-time engineering techniques, this approach greatly utilizes the moving average strategy in order to capture trends in the data that follows time and seasonality and influences changes in the stock demand quantities. Since we are not required to account for the stock quantity by country, we can safely assume that we will generate a result that will be indeed representative of the required total stock quantity for the time in consideration without necessarily considering the required stock supply by Country.

# Assumptions:
In implementing my solution, I used the second approach which is the time series approach. In order to successfully implement my chosen solution effectively I took the liberties stated below.

The time columns were inherited from the same month of the previous year in the data provided and used as train data. The implications of this is that our prediction will have the exact same numbers of rows present in the data from which it was sourced. We expect that In reality, the number of entries will in fact vary but I used it as it is anyway, hence, this in itself is a limitation of my approach. I however expect any conditions that are necessitated by annual seasonality and the trend of growth in the store to be reflected in this solution, hence the Quantity to be predicted for each product to be stocked will vary from the data from the no previous year.

I also adopted the Product code column in the order in which it appeared in the train data for the month of November. This therefore generates an assumption that no new product will be added to the product catalogue and only the product quantity is expected to vary in line with the determinants that are used as my predictors in the development of my algorithm.

# Conclusion:
While this model shows impressive predictive capacity in the test set (with an RMSE of,174.66) , and we expect the same level of performance in the real world, all things remaining equal, it is important for the client to note that real world situations can vary significantly from the predicted model performance due to unforeseen disruptive  events in the real world which may be political, natural, socioeconomic, etc. An example is the COVID pandemic that resulted in very unusual changes in the many performance indices in companies the world over. The client is therefore advised to be sensitive to such conditions as they are not accounted for in this modeling effort.


