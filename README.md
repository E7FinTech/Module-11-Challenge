# Module 11 Challenge

![alt text](11-challenge-image.png)

## Background
You’re a growth analyst at MercadoLibre (Links to an external site.). With over 200 million users, MercadoLibre is the most popular e-commerce site in Latin America. You've been tasked with analyzing the company's financial and user data in clever ways to help the company grow. So, you want to find out if the ability to predict search traffic can translate into the ability to successfully trade the stock.

## What You’re Creating
In a bid to drive revenue, you’ll produce a Jupyter notebook that contains your data preparation, your analysis, and your visualizations for all the time series data that the company needs to understand. You’ll use text and comments to document your findings. And, you’ll answer the question prompts in the instructions. Specifically, this notebook should contain the following:

* Visual depictions of seasonality (as measured by Google Search traffic) that are of interest to the company.

* An evaluation of how the company stock price correlates to its Google Search traffic.

* A Prophet forecast model that can predict hourly user search traffic.

* Answers to the questions in the instructions that you write in your Jupyter notebook.

* (Optional) A plot of a forecast for the company’s future revenue.

Make sure to also create a `MarkdownREADME.md` file that summarizes your models and findings.

## Files
Download the following files to help you get started:
* Module 11 Challenge files

## Instructions
First, configure a Google Colaboratory, or Colab, workspace as follows:

1. Open Google Colab (https://colab.research.google.com/), and then upload your starter notebook.

2. Run the provided code in the “Install and import the required libraries and dependencies” section. Note the following:

    * The first cell installs the necessary libraries into the Google Colab runtime.

    * The second cell imports the dependencies for use in the notebook.

With your workspace configured, you can begin the Challenge. The instructions are divided into four steps and an optional fifth step as follows:

* Step 1: Find unusual patterns in hourly Google Search traffic.

* Step 2: Mine the search traffic data for seasonality.

* Step 3: Relate the search traffic to stock price patterns.

* Step 4: Create a time series model by using Prophet.

* Step 5 (optional): Forecast the revenue by using time series models.

The following subsections detail these steps.

## Step 1: Find Unusual Patterns in Hourly Google Search Traffic
The data science manager asks if the Google Search traffic for the company links to any financial events at the company. Or, does the search traffic data just present random noise? To answer this question, you’ll pick out any unusual patterns in the Google Search data for the company, and connect them to the corporate financial events.

To do so, complete the following steps:

1. Read the search data into a DataFrame, and then slice the data to just the month of May 2020. (During this month, MercadoLibre released its quarterly financial results.) Use hvPlot to visualize the results. Do any unusual patterns exist?

2. Calculate the total search traffic for the month, and then compare the value to the monthly median across all months. Did the Google Search traffic increase during the month that MercadoLibre released its financial results?

## Step 2: Mine the Search Traffic Data for Seasonality
The marketing department realizes that they can use the hourly search data, too. If they can track and predict interest in the company and its platform for any time of day, they can focus their marketing efforts around the times that have the most traffic. This will get a greater return on investment (ROI) from their marketing budget.

To that end, you want to mine the search traffic data for predictable seasonal patterns of interest in the company. To do so, complete the following steps:

1. Group the hourly search data to plot the average traffic by the day of the week (for example, Monday vs. Friday).

2. Using hvPlot, visualize this traffic as a heatmap, referencing `index.hour` for the x-axis and `index.dayofweek` for the y-axis. Does any day-of-week effect that you observe concentrate in just a few hours of that day?

3. Group the search data by the week of the year. Does the search traffic tend to increase during the winter holiday period (Weeks 40 through 52)?

## Step 3: Relate the Search Traffic to Stock Price Patterns
During a meeting with people in the finance group at the company, you mention your work on the search traffic data. They want to know if any relationship between the search data and the company stock price exists, and they ask if you can investigate.

To do so, complete the following steps:

1. Read in and plot the stock price data. Concatenate the stock price data to the search data in a single DataFrame.

2. Note that market events emerged during 2020 that many companies found difficult. But after the initial shock to global financial markets, new customers and revenue increased for e-commerce platforms. So, slice the data to just the first half of 2020 (`2020-01` to `2020-06` in the DataFrame), and then use hvPlot to plot the data. Do both time series indicate a common trend that’s consistent with this narrative?

3. Create a new column in the DataFrame named “Lagged Search Trends” that offsets, or shifts, the search traffic by one hour. Create two additional columns:

    * “Stock Volatility”, which holds an exponentially weighted four-hour rolling average of the company’s stock volatility

    * “Hourly Stock Return”, which holds the percentage of change in the company stock price on an hourly basis

4. Review the time series correlation, and then answer the following question: Does a predictable relationship exist between the lagged search traffic and the stock volatility or between the lagged search traffic and the stock price returns?

## Step 4: Create a Time Series Model by Using Prophet
Now, you need to produce a time series model that analyzes and forecasts patterns in the hourly search data. To do so, complete the following steps:

1. Set up the Google Search data for a Prophet forecasting model.

2. After estimating the model, plot the forecast. How's the near-term forecast for the popularity of MercadoLibre?

3. Plot the individual time series components of the model to answer the following questions:

    * What time of day exhibits the greatest popularity?

    * Which day of the week gets the most search traffic?

    * What's the lowest point for search traffic in the calendar year?

## Step 5 (Optional): Forecast the Revenue by Using Time Series Models
A few weeks after your initial analysis, the finance group follows up to find out if you can help them solve a different problem. Your fame as a growth analyst in the company continues to grow!

Specifically, the finance group wants a forecast of the total sales for the next quarter. This will dramatically increase their ability to both plan budgets and help guide expectations for the company investors.

To do so, complete the following steps:

1. Read in the daily historical sales (that is, revenue) figures, and then apply a Prophet model to the data.

2. Interpret the model output to identify any seasonal patterns in the company revenue. For example, what are the peak revenue days? (Mondays? Fridays? Something else?)

3. Produce a sales forecast for the finance group. Give them a number for the expected total sales in the next quarter. Include the best- and worst-case scenarios to help them make better plans.

## Requirements

## Find Unusual Patterns in Hourly Google Search Traffic (20 points)
To receive all points, you must:

* Read the search data into a DataFrame, and then slice the data to just the month of May 2020. (During this month, MercadoLibre released its quarterly financial results.) (5 points)

* Use hvPlot to visualize the results. (5) points)

* Answer the following question: Do any unusual patterns exist? (2 points)

* Calculate the total search traffic for the month and then compare the value to the monthly median across all months. (6 points)

* Answer the following question: Did the Google search traffic increase during the month that MercadoLibre released its financial results? (2 points)

## Mine the Search Traffic Data for Seasonality (15 points)
To receive all points, you must:

* Group the hourly search data to plot the average traffic by the day of the week (for example, Monday vs. Friday). (4 points)

* Visualize this traffic as a heatmap by using hvPlot, referencing the index.hour as the x-axis and the index.dayofweek as the y-axis. (3 points)

* Answer the following question: Does any day-of-week effect that you observe concentrate in just a few hours of that day? (2 points)

* Group the search data by the week of the year. (4 points)

* Answer the following question: Does the search traffic tend to increase during the winter holiday period (weeks 40 through 52)? (2 points)

## Relate the Search Traffic to Stock Price Patterns (20 points)
To receive all points, you must:

* Read in and plot the stock price data and concatenate the stock price data to the search data in a single DataFrame. (5 points)

* Slice the data to just the first half of 2020 (`2020-01` to `2020-06` in the DataFrame) and then use hvPlot to plot the data. (5 points)

* Answer the following question: Do both time series indicate a common trend that’s consistent with this narrative? (2 points)

* Create three new columns in the DataFrame. The first is "Lagged Search Trends", which offsets, or shifts, the search traffic by one hour. The second is "Stock Volatility", which holds an exponentially weighted four-hour rolling average of the company’s stock volatility. The third is "Hourly Stock Return", which holds the percentage change of the company's stock price on an hourly basis. (6 points)

* Review the time series correlation and then answer the following question: Does a predictable relationship exist between the lagged search traffic and the stock volatility or between the lagged search traffic and the stock price returns? (2 points)

## Create a Time Series Model with Prophet (15 points)
To receive all points, you must:

* Set up the Google search data for a Prophet forecasting model. (3 points)

* Plot the forecast after estimating the model. (4 points)

* Answer the following question: How's the near-term forecast for the popularity of MercadoLibre? (1 point)

* Plot the individual time series components of the model. (4 points)

* Answer the following questions: (3 points)

    * What time of day exhibits the greatest popularity?

    * Which day of the week gets the most search traffic?

    * What's the lowest point for search traffic in the calendar year?

## (Optional) Forecast Revenue by Using Time Series Models (15 points)
To receive all points, you must:

* Read in the daily historical sales (that is, revenue) figures and then apply a Prophet model to the data. (5 points)

* Interpret the model output to identify any seasonal patterns in the company's revenue. For example, what are the peak revenue days? (5 points)

* Produce a sales forecast for the finance group. Give them a number for the expected total sales in the next quarter. Include the best- and worst-case scenarios to help them make better plans. (5 points)

## Coding Conventions and Formatting (10 points)
To receive all points, you must:

* Place imports at the top of the file, just after any module comments and docstrings and before any module globals and constants. (3 points)

* Name functions and variables with lowercase letters and with words separated by underscores. (2 points)

* Follow Don't Repeat Yourself (DRY) principles by creating maintainable and reusable code. (3 points)

* Use concise logic and creative engineering where possible. (2 points)

## Deployment and Submission (10 points)
To receive all points, you must:

* Submit a link to a GitHub repository that’s cloned to your local computer and that contains your files. (4 points)

* Use the command line to add your files the repository. (3 points)

* Include appropriate commit messages for your files. (3 points)

## Code Comments (10 points)
To receive all points, your code must:

* Be well commented with concise, relevant notes that other developers can understand. (10 points)

## Submission
To submit your Challenge assignment, click Submit, and then provide the URL of your GitHub repository for grading.

**NOTE**
You are allowed to miss up to two Challenge assignments and still earn your certificate. If you complete all Challenge assignments, your lowest two grades will be dropped. If you wish to skip this assignment, click Next, and move on to the next module.

Comments are disabled for graded submissions in Bootcamp Spot. If you have questions about your feedback, please notify your instructional staff or your Student Success Manager. If you would like to resubmit your work for an additional review, you can use the Resubmit Assignment button to upload new links. You may resubmit up to three times for a total of four submissions.

