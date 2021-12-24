# matplotlib-challenge
Homework assignment for data science bootcamp, October 2021

## Table of Contents
* [About](#about)
* [Data Sources](#datasources)
* [Analysis and Thoughts](#analysisandthoughts)

## About
* This is the matplotlib homework assignment for the GT Data Science Bootcamp. The challenge is to demonstrate the ability to import data and display it using Pandas and Matplotlib.  
* Within a Jupyter Notebook, data are extracted from the two [Data Sources](#datasources). 

## Procedure
* The data were extracted from the two files (see [Data Sources](#datasources)) and put into Pandas DataFrames which were then merged. 
* DataFrame.duplicated() was used to check for mice with duplicate data. 
  * There was one mouse with duplicate data (more than one data point per timestamp)
  * This mouse had conflicting data - different tumor sizes and metastatic sites for the same timestamp. Therefore, the mouse was deleted alltogether since there is no way to justify which data to use. 
* The .loc function was used to remove all instances of the duplicated mouse. 
  * There were 249 mice originally, now there are 248 mice in the DataFrame. 
  * There were 13 rows removed, even though there were only 10 rows with duplicate Mouse ID and Timepoint. 
* A summary table was created using df.groupby() and the .mean(), .median(), .var(), .std() and .sem() groupby object functions and pd.DataFrame(). A second summary table was created in one line using df.groupby() and the .agg() groupby object function. 
* Bar and pie charts were created using both Pandas and pyplot. 

## Data Sources
The data for this challenge can be found in the following two files:
/Data/Mouse_metadata.csv 
/Data/Study_results.csv

## Analysis and Thoughts
1. Ramicane and Capomulin seem to have the lowest tumor size amongst all the treatment regimens. The other treatment options, including placebo, were centered around about 60 mm3, while these two were both below 40 mm3. See my box plot with all treatment regimens. 
2. From the bar chart, we can see that Ramicane and Capomulin also have the most timepoints compared to all the treatment regimens. This could mean that these mice lasted longer on the whole than the mice treated with the other drugs. However, it is unknown if the number of mice receiving each drug is the same. This could cause a difference in the number of timepoints and should be investigated before a definitive statement is made. 
3. There was a pretty high correlation between mouse weight and tumor size in mice receiving Capomulin. This could be because a larger mouse tends to grow a proportionally large tumor, or it could also be that the larger tumors are actually increasing the overall weight of the mice. 
4. From the summary dataframes, the mean tumor size for Ramicane and Capomulin were significantly lower than the means for the other tumors - about 40 mm3 compared to between 52 mm3 and 55 mm3 for the other drugs and the placebo. This makes sense since the final tumor sizes were much smaller, but were the initial tumor sizes all about even? Did Ramicane and Capomulin actually lower the size of the tumors more than the other drugs or did they just happen to be given to mice with smaller tumors at the beginning? 
