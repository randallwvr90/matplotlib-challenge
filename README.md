# matplotlib-challenge
Homework assignment for data science bootcamp, October 2021

## Table of Contents
* [About](#about)
* [Data Sources](#datasources)
* [Analysis and Thoughts](#analysisandthoughts)

## About

## Procedure
* The data were extracted from the two files (see [Data Sources](#datasources)) and put into Pandas DataFrames which were then merged. 
* DataFrame.duplicated() was used to check for mice with duplicate data. 
  * There was one mouse with duplicate data (more than one data point per timestamp)
  * This mouse had conflicting data - different tumor sizes and metastatic sites for the same timestamp. Therefore, the mouse was deleted alltogether since there is no way to justify which data to use. 
* The .loc function was used to remove all instances of the duplicated mouse. 
## Data Sources
The data for this challenge can be found in the following two files:
/Data/Mouse_metadata.csv 
/Data/Study_results.csv

## Analysis and Thoughts
