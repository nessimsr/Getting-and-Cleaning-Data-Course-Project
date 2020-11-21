# Summary

The run_analysis.R script performs the data preparation and cleaning of the dataset

## Downloading the dataset
Dataset downloaded and extracted under the folder called FUCI HAR Datase

## Assigning each data to variables
1. features - features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
2. activities - list of activities performed when the corresponding measurements were taken and its codes
3. subject_test - contains test data of 9/30 volunteer test subjects being observed
4. x_test - contains recorded features test data
5. y_test - contains test data of activities’code labels
6. subject_train - contains train data of 21/30 volunteer subjects being observed
7. x_train - contains recorded features train data
8. y_train - contains train data of activities’code labels

## Merging the training and test sets to create one data set using rbind and cbind

1. X <- rbind(x_train, x_test) - created by merging x_train and x_test using rbind() function
2. Y <- rbind(y_train, y_test) - created by merging y_train and y_test using rbind() function
3. Subject <- rbind(subject_train, subject_test) - created by merging subject_train and subject_test using rbind() function
4. Merged_Data <- cbind(Subject, Y, X) -created by merging Subject, Y and X using cbind() function

## Finding the mean and standard deviation for each measurement.
TidyData <- Merged_Data %>% select(subject, code, contains("mean"), contains("std"))

## Labeling the data set with descriptive variable names
- All Acc in column’s name replaced by Accelerometer
- All Gyro in column’s name replaced by Gyroscope
- All BodyBody in column’s name replaced by Body
- All Mag in column’s name replaced by Magnitude
- All start with character f in column’s name replaced by Frequency
- All start with character t in column’s name replaced by Time
- All of -mean(),-std(),-freq() changed to "Mean", "STD" and "Frequency" respectively 

# Finilized Data
-Finilized thee clean data with averages of each variable for each activity and each subject and saved it as Final data to a txt file
