# Predict-travel-time-using-XGBoost
The NYC taxi dataset is used to predict the travel time between two given location coordinates using the XGBoost algorithm.

Data_Preprocessing_XGBoost.ipynb

This file performs the following tasks - 

1)Data pre-processing:
* The NYC taxi dataset is loaded into a Pandas data frame.
* The unwanted columns are removed.
* The PULocationID and DOLocationID are used to identify the corresponding taxi zones and their respective location coordinates which are stored as new attributes in the dataset.
* The datetime column is converted from string to datetime format for further processing.
* The date, day of week, month and hour of the day are stored as separate new attributes.

2) XGBoost model:
* The preprocessed data is split into train, test and validation sets. All the columns except trip_duration are considered as input features to the ML model.
* RootMeanSquareLogError is used as the evaluation metric.
* The XGBoost model is trained with the specified parameters on the train set.
* The model is then used to predict trip duration on the test set.
* The Mean Absolute Error (MAE) is calculated to determine the performance of the XGBoost model.


