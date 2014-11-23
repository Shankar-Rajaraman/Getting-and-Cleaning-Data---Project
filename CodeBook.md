---
title: "CodeBook.md"
author: "Shankar Rajaraman"
date: "Saturday, November 22, 2014"
output: word_document
---

The table that is explained in this document is the final tidy output "Tidy_Avg_Summary_Final" ( or the txt file ""Final_Tidy_Avg_Summary.txt") submitted for the assignment. 

"Tidy_Avg_Summary_Final" has 4 variables(columns) and 11880 rows. The column variables are explained below.

=================DATA DICTIONARY- Tidy_Avg_Summary_Final============ 

Subject -1st variable/column

        -Value Type - Integer factor. 
        
        - The people who have been experimented with -> 30 people in total with 21 for train and 9 for    test. Integer factors are assigned. values are  
        1: 1st subject
        2: 2nd subject
        .:
        .:
        28: 28th subject
        29: 29th subject
        30: 30th subject
        
        subjects 2, 4, 9, 10, 12, 13, 18, 20, 24 are assigned to test and
        subjects  1, 3, 5, 6, 7, 8, 11, 14, 15, 16, 17, 19, 21, 22, 23, 25, 26, 27, 28, 29, 30 are  assigned to train.
        


Activity- 2nd variable/column


	- Value Type - Character factor( Originally integer)
        - There are 6 types of activity originally mapped to integer values shown in parenthesis.
        WALKING : Activity(1)
        WALKING_UPSTAIRS: Activity(2)
        WALKING_DOWNSTAIRS: Activity(3)
        SITTING: Activity(4)
        STANDING: Activity(5)
        LAYING : Activity(6)
        
        
        
Mean_Std_Variables - 3rd variable/column
        
        
        - Value Type - Character factor
        - These are from original entries of the "feature" table representing  different measurement signals. The variables are culled out only for the "mean"  and "std.dev" variables shown below. The following are the what the abbreviations stand for.
        t- represents time domain,
        f- frequency
        body- Body
        Acc - acceleration
        gyro - angular measurements.
        jerk -jerks introduced by either body/gyro. 
        Mag- magnitude
        mean - mean or average
        std -standard deviation
        X- X component of signal
        Y - Y component of signal
        Z- Z component of signal
Sample interpretation -tBodyAcc-mean-X -> Mean of X-component of the body acceration taken in time domain.The 66 unique entries are listed below.

        tBodyAcc_mean_X :
        tBodyAcc_mean_Y :
        tBodyAcc_mean_Z :
        tGravityAcc_mean_X :
        tGravityAcc_mean_Y :
        tGravityAcc_mean_Z :
        tBodyAccJerk_mean_X :
        tBodyAccJerk_mean_Y :
        tBodyAccJerk_mean_Z :
        tBodyGyro_mean_X :
        tBodyGyro_mean_Y :
        tBodyGyro_mean_Z :
        tBodyGyroJerk_mean_X :
        tBodyGyroJerk_mean_Y :
        tBodyGyroJerk_mean_Z :
        tBodyAccMag_mean :
        tGravityAccMag_mean :
        tBodyAccJerkMag_mean :
        tBodyGyroMag_mean :
        tBodyGyroJerkMag_mean :
        fBodyAcc_mean_X :
        fBodyAcc_mean_Y :
        fBodyAcc_mean_Z :
        fBodyAccJerk_mean_X :
        fBodyAccJerk_mean_Y :
        fBodyAccJerk_mean_Z :
        fBodyGyro_mean_X :
        fBodyGyro_mean_Y :
        fBodyGyro_mean_Z :
        fBodyAccMag_mean :
        fBodyBodyAccJerkMag_mean :
        fBodyBodyGyroMag_mean :
        fBodyBodyGyroJerkMag_mean :
        tBodyAcc_std_X :
        tBodyAcc_std_Y :
        tBodyAcc_std_Z :
        tGravityAcc_std_X :
        tGravityAcc_std_Y :
        tGravityAcc_std_Z :
        tBodyAccJerk_std_X :
        tBodyAccJerk_std_Y :
        tBodyAccJerk_std_Z :
        tBodyGyro_std_X :
        tBodyGyro_std_Y :
        tBodyGyro_std_Z :
        tBodyGyroJerk_std_X :
        tBodyGyroJerk_std_Y :
        tBodyGyroJerk_std_Z :
        tBodyAccMag_std :
        tGravityAccMag_std :
        tBodyAccJerkMag_std :
        tBodyGyroMag_std :
        tBodyGyroJerkMag_std :
        fBodyAcc_std_X :
        fBodyAcc_std_Y :
        fBodyAcc_std_Z :
        fBodyAccJerk_std_X :
        fBodyAccJerk_std_Y :
        fBodyAccJerk_std_Z :
        fBodyGyro_std_X :
        fBodyGyro_std_Y :
        fBodyGyro_std_Z :
        fBodyAccMag_std :
        fBodyBodyAccJerkMag_std :
        fBodyBodyGyroMag_std :
        fBodyBodyGyroJerkMag_std :


Average - 4th variable/column 

        - Value Type - numeric

        This is the average value of each entry of the 3rd variable ("Mean_Std_Variables") grouped by subject and activity. Sample values look like : 0.2215982, 0.2612376, 0.2789176, 0.2773308, 0.2891883, 0.2554617.
        
#######################################################################################################

