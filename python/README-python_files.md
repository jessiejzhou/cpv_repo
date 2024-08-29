# Stock Info
This file uses our master dataset to grab publicly traded companies' financial info from Yahoo Finance. Workflow is: grabbing the company ticker symbol from the excel file, using this with an API to pull from yfinance, and then uploading into a new dataset. This new dataset is then attached as a new sheet into the original excel.

## Using this file

### Setting up the environment
To begin, download [Python](https://www.python.org/downloads/). Then, using pip (package manager, should come with downloading Python), download jupyterlab. Jupyterlab is essentially a workbook for writing and running code. You can install by running the following code in terminal:

`pip install jupyterlab` or `pip3 install jupyterlab`

Try either command in case one of them doesn't work. This is actually the way to install packages in python; packages are like toolboxes that have prewritten functions to help with spefific tasks. The general format is:

`pip install [package_name]`

If this doesn't work, try using `pip3` in place of `pip`.

To open jupyterlab, go to terminal and enter the command: `jupyter lab`

### Code Breakdown
The steps are explained in the Python file for ease of reference. We first load the our excel file, where the path is stored in `file_path` and we choose the sheet that has the ticker symbols. Then, we write out functions that pull info using the yfinance API. This is an open-source python library, unaffiliated with Yahoo but uses Yahoo's publicly available APIs to get market data. 

After writing the functions, we loop through all of the ticker symbols and apply the functions to each one. Then, we store the values in a new dataframe.

With the new dataframe `result`, we use another [API](https://www.exchangerate-api.com/) to convert non-USD values into USD. It's free to sign up, and once your account is created it will generate an API key for you to use. Replace `api_key` with the one created for your account. We then convert the currency, select the columns we want, and upload this new sheet to our original file.

Then at the end, I pivot the `Master Data` to long format.

### Using this code
Running this is super simple; there are only a few changes required for your use. 

First and most importantly, ⚠️ **if the original excel file name is modified or if the file path is changed (i.e. moved into different folders on your computer), `file_path` needs to be updated accordingly**. ⚠️ You can easily get the path by right clicking on your file in jupyterlab and selecting "Copy Path." 

![pixil-frame-0](https://github.com/user-attachments/assets/d656da05-c5c1-4a8f-b481-e8ec60380204)


⚠️ **Please update the `destination_path` variable _at the very end_ to the desired folder where you want `survey_long` to be stored in the same way** ⚠️

The second change to be made is the API key for ExchangeRate-API that I mentioned previously. This is optional but **highly reccomended**. 

If the file path is set up correctly, all the work required is to click the run button at the top, the one that resembles a fast forward button:

![pixil-frame-0 (2)](https://github.com/user-attachments/assets/d4b45233-a1f9-40de-914b-234d5224f0cd)

Once you've done this, the sheet should be uploaded into the original file!


# Company Upload
This file utilizes the hivebrite API to push changes onto the website. The only thing you need to change is `file_path` and make sure `sheet_name' is correct in this line:

`df = pd.read_excel(file_path, sheet_name="industry_only")`

In this example, we're pulling CVC industry and the sheet on the excel file is called "industry_only." Then, just click run.
