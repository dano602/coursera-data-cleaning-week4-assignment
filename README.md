# README

## Summary

This project is part of the *Peer-graded Assignment: Getting and Cleaning Data Course Project*.

It contains one main R script to create a clean data set from the 'UCI HAR Dataset' 
available at:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

There is one main R script for creating a clean data set file named "clean_dataset.txt".

Additionally, an aggregated data set named "tidy_dataset.txt" is created. It contains the average 
of each variable for each activity and each subject.

## Run

Execute the R script:

    run_analysis.R

which will create the result data files "clean_dataset.txt" and "tidy_dataset" in the working directory. 

The script executes the following steps:

1. Load the individual data files of the training and test sets and merge them into one data table
2. Filter the data table to select only mean and standard deviation columns
3. Load labels and levels to the activity column and convert it into a factor variable
4. Assign cleaned feature strings as column names for the feature measurements
5. Merge test and training subsets into one final cleaned data set
6. Create another data set with average of each variable for each activity and each subject

## Dependencies

The script uses the following libraries:

* data.table
* dplyr
* reshape2

## Functions

**load.data.subset**

Load subset of the full 'UCI HAR Dataset'.

* The function loads a subset of the full data set. The steps are:
** load features table selecting only the std/mean columns 
** load activities, assign descriptive labels (convert into a factor variable)
** load subjects
** filter the data table to select only mean and standard deviation columns
** load labels and levels to the activity column and convert it into a factor variable
** assign cleaned feature strings as column names for the feature measurements
** create feature table appending the activities and subjects columns

**create.clean.dataset**

Function to merge the two data tables created for the 'train' and 'test' subsets.

**create.clean.dataset.file**

Function to create the data set file based on the clean data set table.

**create.tidy.dataset**

Function to create the tidy data set based on the clean data set.

**create.tidy.dataset.file**

Function to create the tidy data set file based on the clean data set table.
