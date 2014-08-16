## Source Data
The data comes from the UCI Human Activity Recognition Using Smartphones Data Set. Human Activity Recognition database built from the recordings of 30 subjects performing activities of daily living (ADL) while carrying a waist-mounted smartphone with embedded inertial sensors.

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

For each record in the dataset it is provided: 
- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration. 
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment. 

##Transformation
The run_analysis.R script performs the following manipulations to the source data:
- Merges the training and the test sets to create one data set
- Extracts only the measurements on the mean and standard deviation for each measurement
- Uses descriptive activity names to name the activities in the data set
- Appropriately labels the data set with descriptive variable names
- Creates a second, independent tidy data set with the average of each variable for each activity and each subject
- Writes the second tidy dataset to the working directory as "tidy_dat.txt"

##Variables
From the original 561 features provided in the source dataset, only the 79 mean and standard deviation values are retained in the returned tidy dataset. **The variables that are angular measurements of mean variables are ignored as they are not direct mean estimates.**

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 

These signals were used to estimate variables of the feature vector for each pattern:  
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.

- tBodyAcc-XYZ
- tGravityAcc-XYZ
- tBodyAccJerk-XYZ
- tBodyGyro-XYZ
- tBodyGyroJerk-XYZ
- tBodyAccMag
- tGravityAccMag
- tBodyAccJerkMag
- tBodyGyroMag
- tBodyGyroJerkMag
- fBodyAcc-XYZ
- fBodyAccJerk-XYZ
- fBodyGyro-XYZ
- fBodyAccMag
- fBodyAccJerkMag
- fBodyGyroMag
- fBodyGyroJerkMag

The set of variables that were estimated from these signals are: 
- mean: Mean value
- std: Standard deviation

Additionally, the subject number and activity performed are attached to each measurement feature as:
- subjectNum (the subject's number, an integer from 1 to 30)
- activity (1 of 6 descriptive activity labels):
- - WALKING
- - WALKING_UPSTAIRS
- - WALKING_DOWNSTAIRS
- - SITTING
- - STANDING
- - LAYING


The list of features is as follows:
- tBodyAccmeanX
- tBodyAccmeanY
- tBodyAccmeanZ
- tBodyAccstdX
- tBodyAccstdY
- tBodyAccstdZ
- tGravityAccmeanX
- tGravityAccmeanY
- tGravityAccmeanZ
- tGravityAccstdX
- tGravityAccstdY
- tGravityAccstdZ
- tBodyAccJerkmeanX
- tBodyAccJerkmeanY
- tBodyAccJerkmeanZ
- tBodyAccJerkstdX
- tBodyAccJerkstdY
- tBodyAccJerkstdZ
- tBodyGyromeanX
- tBodyGyromeanY
- tBodyGyromeanZ
- tBodyGyrostdX
- tBodyGyrostdY
- tBodyGyrostdZ
- tBodyGyroJerkmeanX
- tBodyGyroJerkmeanY
- tBodyGyroJerkmeanZ
- tBodyGyroJerkstdX
- tBodyGyroJerkstdY
- tBodyGyroJerkstdZ
- tBodyAccMagmean
- tBodyAccMagstd
- tGravityAccMagmean
- tGravityAccMagstd
- tBodyAccJerkMagmean
- tBodyAccJerkMagstd
- tBodyGyroMagmean
- tBodyGyroMagstd
- tBodyGyroJerkMagmean
- tBodyGyroJerkMagstd
- fBodyAccmeanX
- fBodyAccmeanY
- fBodyAccmeanZ
- fBodyAccstdX
- fBodyAccstdY
- fBodyAccstdZ
- fBodyAccmeanFreqX
- fBodyAccmeanFreqY
- fBodyAccmeanFreqZ
- fBodyAccJerkmeanX
- fBodyAccJerkmeanY
- fBodyAccJerkmeanZ
- fBodyAccJerkstdX
- fBodyAccJerkstdY
- fBodyAccJerkstdZ
- fBodyAccJerkmeanFreqX
- fBodyAccJerkmeanFreqY
- fBodyAccJerkmeanFreqZ
- fBodyGyromeanX
- fBodyGyromeanY
- fBodyGyromeanZ
- fBodyGyrostdX
- fBodyGyrostdY
- fBodyGyrostdZ
- fBodyGyromeanFreqX
- fBodyGyromeanFreqY
- fBodyGyromeanFreqZ
- fBodyAccMagmean
- fBodyAccMagstd
- fBodyAccMagmeanFreq
- fBodyBodyAccJerkMagmean
- fBodyBodyAccJerkMagstd
- fBodyBodyAccJerkMagmeanFreq
- fBodyBodyGyroMagmean
- fBodyBodyGyroMagstd
- fBodyBodyGyroMagmeanFreq
- fBodyBodyGyroJerkMagmean
- fBodyBodyGyroJerkMagstd
- fBodyBodyGyroJerkMagmeanFreq

##Output tidy dataset
The tidy dataset that is generated by the script contains means of all 79 variables stratified by subject number and activity.