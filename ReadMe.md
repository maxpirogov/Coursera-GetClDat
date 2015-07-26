# Getting and cleaning data
Class assignment to create a tidy data set of wearable computing data (source http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)

##Files in the repo

 - README.md - standard markdown file
 - CodeBook.md -- codebook describing variables, the data and transformations performed
 - run_analysis.R -- actual R code

To create one R script called run_analysis.R that does the following: 
 - Merges the training and the test sets to create one data set. 
 - Extracts only the measurements on the mean and standard deviation for each measurement. 
 - Uses descriptive activity names to name the activities in the data set 
 - Appropriately labels the data set with descriptive activity names. 
 - Creates a second, independent tidy data set with the average of each variable for each activity and each subject.


### Tasks 1:
Read "test" and "training" files: y_test.txt, subject_test.txt and X_test.txt.
Combine the files to a data frame in the form of subjects, labels, the rest of the data.

### Task 2:

Read the features from features.txt and filter it to only leave features that are either means ("mean()") or standard deviations ("std()"). The reason for leaving out meanFreq() is that the goal for this step is to only include means and standard deviations of measurements, of which meanFreq() is neither.
A new data frame is then created that includes subjects, labels and the described features.

### Task 3:

Read the activity labels from activity_labels.txt and replace the numbers with the text.

### Task 4:

Make a column list (includig "subjects" and "label" at the start)
Tidy-fy the list by removing all non-alphanumeric characters and converting the result to lowercase
Apply the now-good-columnnames to the data frame

### Task 5:

Create a new data frame by finding the mean for each combination of subject and label. It's done by aggregate() function
Final step:

Write the tidy data to a file "tidy_data.txt".