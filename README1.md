---
title: "Readme.md"
author: "Shankar Rajaraman"
date: "Sunday, September 21, 2014"
output: word_document
---

Getting-and-Cleaning-Data---Project
===================================

The github folder - "https://github.com/Shankar-Rajaraman/Getting-and-Cleaning-Data---Project" contains all the necessary files 
required to be submitted for the project  coursework - "Getting and Cleaning Data" of the Data Science specialization in Coursera. 
The project objective is to create a tidy data set from a raw wearable computing dataset provided by the courese. The folder 
contains 4 files viz.

1) README.md  -->This present file
2.)run_analysis.R --> A R script file that contains that code that convert the raw(untidy) file to a tidy file. The procedural 
details of how the script works is explained below.
3.)CodeBook.md--> A codebook explaining all the variables of the tidy data set and its details.


How the run_anlaysis.R script works
==================================

All files are downloaded to "C:\Shankar_PC\CopiedFromFreeAgent\Coursera\Getting and Cleaning Data\PROJ1\UCI HAR Dataset" folder


Relvant data files used 
-----------------------
1.) X_Test (2947x 561) and X_Train(7352 x 561) datasets contain the rawdata  data. 
2.) subject_test (2947x1, 7 people) and subject_train ( 7352 x1, 21 people) contain the subjects( the people) on whom the 
experiment was performed. 
3.) features (561x2) contains all the measurment variables ( like acceleration's mean,std.dev, min, max etc) 
4.) activity_labels(6x2) maps the activity names( like walking,standing. etc) to its integer values.
5.) y_test (2947 x 1) and y_train(7352 x 1) contain the activities performed by the subjects as integer values.


Procedure
---------

1.) X_test, y_test,subject_test,features,activity_labels are all read as table from the home directory.

2.) X_test is converted to "tbl_df"  format ( for easy manipulation and to use group_by & summarize functions later)- 2947 x 561

3.) X_test is  assigned column names from features table -- 561 variables

4.) Only the variables that contain "mean()" and "std()" are selected from the features table as "meannames" and "stdnames".

5.) X_test is subsetted with only the column names from "meannames" and "stdnames". After this X_test contains only the mean/std 
variables--66 variable in total.

6.) Prepend (use cbind)the subject_test and activity_labels to X_test--has 2947 rows and 68 columns. 

7.) Label the the first 2 column names as "Subject" and "Activity".

8.) Change the integer values of the "Activity" column to its string equivalent for easy reading/interpretation.

9.) Repeat step 1-8 for the train datsets- X_train,y_train,subject_train.

10.) Rowbind the final X_train(7352x561) and final X_test(2947x561) datasets into "X_train_test_Act_Sub" (10299x68).

11.) Rename the column names of  "X_train_test_Act_Sub" into descriptive variable names (STEP 4 of the project). 
 
12.) Change "Subject" and "Activity"  of  "X_train_test_Act_Sub" to factor variables to facilitate grouping.

13.) Group "X_train_test_Act_Sub" by "Subject" and "Activity" using group_by function in library(dplyr). Call this interim table  
"m"(10299x68).

14.) Use the summarize function on "m" with the mean function on all the mean and std.dev variable columns ( columns 3:68) to 
calculate their averages. Call the variable "Avg_Summary_by_Sub_Act" (180x68) 

15.) After this step , "Avg_Summary_by_Sub_Act"  will contain 66 average-value variables + "Subject" +"Activity" columns for a 
total of 68 columns and 180 rows. 

16)The data of  "Avg_Summary_by_Sub_Act" has the averages of all columns grouped by "Subject" and "Activity" but the data is NOT 
tidy yet as the average columns are still variables of the same kind. 

17.) So a tidy data is created  "Tidy_Avg_Summary_Final" (11880x4) usign the "gather" function in library(tidyr). The four columns 
are: "Subject","Activity", "Mean_Std_Variables","Average".  

18.) The "Tidy_Avg_Summary_Final" is tidy 
        a.) as each row is a unique observation 
	b.) and each column is a variable. 
	c.) This one table gives complete information without redundancy for the average calculation required.
19.) Finally the  "Tidy_Avg_Summary_Final" is written into a .txt file "Final_Tidy_Avg_Summary.txt" in the home directory.

References:
==========

1.) Problem understanding and clarification from the discussion forum  threads 
" https://class.coursera.org/getdata-007/forum/list?forum_id=10009"
2.) David Hood's (Community TA) clarification was very helpful
"https://class.coursera.org/getdata-007/forum/thread?thread_id=49"



