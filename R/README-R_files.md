# Overview

There are three main files you will need: master.Rmd, pivot_df.Rmd, and multiple_answers.Rmd:

- master: pulls the four years of data into one
- pivot_df: reshapes the master data into long format, we need this for Tableau
- multiple_answers: pulls questions with multiple answers and breaks them down line by line. For the relational database.

# File Paths:

You will need to update file_path and destinations to where the data is stored on your local machine. **There is a difference between FILE path and FOLDER path, for example, file_path would be something like:<br><br>_"/Users/counterpartventures/Desktop/Data/Survey_Data_V5.xlsx"_ <br><br>whereas folder path is:<br><br>_"/Users/counterpartventures/Desktop/Data"_**

You will have to choose which path to use according to my instructions below.


# To run the scripts:

Install R and RStudio [here](https://posit.co/download/rstudio-desktop/). Then you should be able to open and edit files.
Click "Run All" or Option + Command + R to run the script. 

![pixil-frame-0 (3)](https://github.com/user-attachments/assets/fab193f7-7dff-4dd2-8f4f-fb3c17873a45)


# Master

This is the most important file. If there are any changes to the yearly survey data, then run this script and you will get updates in "Master Data."

⚠️ **Please edit `file_path` to the _FILE_ path of Survey_Data on your local machine.** ⚠️


# pivot_df

This is the file to pivot the original "Master Data" into long format. Run it to get a long version of your data. 

⚠️ **please edit `file_path` to the file path of Survey_Data on your local machine. Also edit `destination_path` to the _FOLDER_ path, ‼️ NOT FILE path‼️, where you want `survey_long` to be stored.** ⚠️

# multiple_answers

This takes all of the questions in the survey that have multiple selection options, and breaks each selection down into a row by CVC. Primary outputs are: 
- multiple_response_qs_long.xlsx
- multiple_response_qs.xlsx
  
These are used in the Tableau relational database.

⚠️**please edit `file_path` to the _FILE_ path of Survey_Data on your local machine, as well as `destination_path` to the _FOLDER_ path where you want `multiple_response_qs_long.xlsx` and `multiple_response_qs.xlsx` to be stored. Follow the previous instructions to get the correct FILE and FOLDER paths.** ⚠️
