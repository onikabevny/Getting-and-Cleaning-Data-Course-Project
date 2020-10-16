The run_analysis.R script performs the data preparation and then followed by the 5 steps required as described in the course project’s definition.

1. Download the dataset

* Dataset downloaded and extracted under the folder called UCI HAR Dataset

2. Assign each data to variables

* features <- features.txt
 The features selected for this database come from the accelerometer and gyroscope

* activities <- activity_labels.txt 
List of activities performed when the corresponding measurements were taken and its codes (labels)
* subjectTest <- test/subjectTest.txt 
 contains test data of 9/30 volunteer test subjects being observed

* featuresTest <- test/X_test.txt
 contains recorded features test data

* activityTest <- test/y_test.txt
 contains test data of activities’code labels

* subjectTrain <- test/subject_train.txt 
 contains train data of 21/30 volunteer subjects being observed

* featuresTrain <- test/X_train.txt 
 contains recorded features train data

* activutyTrain <- test/y_train.txt 
 contains train data of activities’code labels

3. Merges the training and the test sets to create one data set

* Subject is created by merging subjectTrain and subjectTest using rbind() function

* activity is created by merging activityTrain and activityTest using  rbind() function

* features is created by merging featuresTrain and featureTest using  rbind() function

* CompleteData is created by merging Subject,features and activity using cbind() function

4. Extracts only the measurements on the mean and standard deviation for each measurement

* TidyData (10299 rows, 88 columns) is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement

5. Uses descriptive activity names to name the activities in the data set

* Entire numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable

6. Appropriately labels the data set with descriptive variable names

* code column in TidyData renamed into activities

* All Acc in column’s name replaced by Accelerometer

* All Gyro in column’s name replaced by Gyroscope

* All BodyBody in column’s name replaced by Body

* All Mag in column’s name replaced by Magnitude

* All start with character f in column’s name replaced by Frequency

* All start with character t in column’s name replaced by Time

7. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject

* FinalData is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.

* Export FinalData into Tidy.txt file.
