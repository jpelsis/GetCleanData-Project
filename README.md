## README for run_analysis.R

###REQUIREMENTS
- reshape2 R library
- One of the following:
	- The full Human Activity Recognition Using Smartphones Data Set located in the working directory as originally provided
	- A working internet connection for the dataset to be downloaded

###DESCRIPTION OF SCRIPT
The run_analysis.R script contains a loading function to download, unzip, import and clean the original Human Activity Recognition Using Smartphones Data Set.

After the definition of the 'loadactivitydata' function, the function is called setting the options for verbose and DL using globally defined variables at the top of the script. These values are set to TRUE so that there is no assumption necessary about the name or location of the dataset on the user's machine. Once the full, clean dataset has been loaded, it is subsetted into a new dataset that contains only subject number, activity, mean feature estimates, and standard deviation feature estimates. Finally, the mean of each of these 79 features by each combination of subject and activity is calculated and the dataset is reshaped so that the feature means are stratified by subject number and activity. This tidy dataset is then saved in the working directory as 'tidy_data.txt'

###DESCRIPTION OF DATA
A detailed description of the data can be found in the CodeBook.md file in this repository
###SAMPLE OF THE TIDY DATASET

```
##    subjectNum           activity tBodyAccmeanX tBodyAccmeanY tBodyAccmeanZ
## 1           1            WALKING        0.2773     -0.017384       -0.1111
## 2           1   WALKING_UPSTAIRS        0.2555     -0.023953       -0.0973
## 3           1 WALKING_DOWNSTAIRS        0.2892     -0.009919       -0.1076
## 4           1            SITTING        0.2612     -0.001308       -0.1045
## 5           1           STANDING        0.2789     -0.016138       -0.1106
## 6           1             LAYING        0.2216     -0.040514       -0.1132
## 7           2            WALKING        0.2764     -0.018595       -0.1055
## 8           2   WALKING_UPSTAIRS        0.2472     -0.021412       -0.1525
## 9           2 WALKING_DOWNSTAIRS        0.2776     -0.022661       -0.1168
## 10          2            SITTING        0.2771     -0.015688       -0.1092
## 11          2           STANDING        0.2779     -0.018421       -0.1059
## 12          2             LAYING        0.2814     -0.018159       -0.1072
```
