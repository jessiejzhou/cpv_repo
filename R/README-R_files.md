# To run the scripts:

Install R and RStudio [here](https://posit.co/download/rstudio-desktop/). Then you should be able to open and edit files.
Click "Run All" or Option + Command + R to run the script. 

![pixil-frame-0 (3)](https://github.com/user-attachments/assets/fab193f7-7dff-4dd2-8f4f-fb3c17873a45)


# Master

This is the most important file. If there are any changes to the yearly survey data, then run this script and you will get updates in "Master Data."

⚠️**please edit `file_path` to the file path of Survey_Data on your local machine.**⚠️


# pivot_df

This is the file to pivot the original "Master Data" into long format. Run it to get a long version of your data. 

⚠️**please edit `file_path` to the file path of Survey_Data on your local machine, as well as `destination_path` to the folder where you want `survey_long` to be stored.**⚠️
