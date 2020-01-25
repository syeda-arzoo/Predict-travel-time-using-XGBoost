# Predict-travel-time-using-XGBoost
Use the NYC taxi dataset to predict travel time between two location coordinates using XGBoost

Data_Preprocessing_XGBoost.ipynb

This file performs the following three tasks - 
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
* The Mean Absolute Error (MAE) is calculated for comparison with the LightGBM model in the next stage.

3)Lookup Table:
* A sample set of 11 and 25 location coordinates is saved in test_locations11 and test_locations25 respectively. 
* These sample destination points along with a sample date time value are passed as input to the trained XGBoost model. 
* The model predicts the trip duration for each pair of location coordinates, the results of which are stored as a lookup table to be fed to the Genetic algorithm in the next stage.
