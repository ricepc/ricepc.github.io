---
layout: post
title: Using Python to football
cover-img: /assets/img/PennStat.png
#thumbnail-img: /assets/img/thumb.png
#share-img: /assets/img/path.jpg
tags: [Optimization, Python, Pyomo]
---

# Summary:
The Covid-19 pandemic has presented many industries with an interesting problem, Is it possible to model customer actions as they begin to adjust to the new normal? Using Data provided by New York's Metropolitan Transportation Authority, I was able to create a reliable firecast. 

# Retrieving and Cleaning the Data
All data for this project can be found on Metropolitan Transportation Authority's (MTA) [website](http://web.mta.info/developers/turnstile.html) or on [my github page.](https://github.com/ricepc/MTA_Turnstile_Data) 

Each week the MTA posts a .txt file with the daily number of entries and exits from all New York subway stations. My goal in this analysis was to focus on only the data from Penn Station to better understand what patterns exist within tdata and how they may be used to predict future ridership as New Yorkers begin to adjust to the new normal.

The data provided by MTA shows a running total of customers that have entered and exited through a given turnstile. For this analysis, I calculated the daily traffic for each turnstile and then aggrigated up to get the total traffic at the station for each day. 

# Visualizing the Data
With any time series project the first step is to plot the data vs time. Below we see just how big of an impact Covid-19 has had on travel through Penn Station. Prior to the Pandemic, a typical weekday could bring upwards of 300,000 people through the station. Just five months later and that number has dropped to around 70,000. There is some seasonality within each week and across each year which is to be expected since most of New York's traffic comes from commuters that don't need to travel on weekend and tourism that fluctuates during the holiday seasons. 
![Time Series Data](https://github.com/ricepc/ricepc.github.io/raw/master/assets/Turnstile%20_Images/Full_TS_AutoPlot.JPG)

For the sake of modeling I have chosen to only look at data starting from April 2020 (The first month after New York shut down). The data prior to the cutoff could be valuable in some prediction models, however its reasonable to assume that traffic patterns of the two groups are very different given the context of the pandemic. 
![Covid Time Series Data](https://github.com/ricepc/ricepc.github.io/raw/master/assets/Turnstile%20_Images/Covid_TS_Autoplot.jpeg)

Looking at the data by weekday, it is apparent that there is less traffic on weekends. This make senses considering commuters do not usually have to enter the city on these days. There are three data points, all on Mondays, that appear to have large deviations from the trend. These correspond with Memorial Day, Labor Day, and Columbus Day all of which mean less workers.
![Covid ggseason](https://github.com/ricepc/ricepc.github.io/raw/master/assets/Turnstile%20_Images/Covid_ggseason.png)

![Covid ssubseries](https://github.com/ricepc/ricepc.github.io/raw/master/assets/Turnstile%20_Images/covid_ggsubseries.png)

# Forecast Models
The two models I used for my forecast are exponential smoothing and ARIMA. Both offer techniques to handle the data's seasonality and trend well.  
## Exponential Smoothing
Exponential smoothing models can be broken into three compentents: Error, Trend, Seasonality. Each of these compentents contributes to a weighted average that predicts

## ARIMA
The first step to building an ARIMA model is to check if any differencing is necessary to get the data to be stationary. In this case first order seasonal differencing was required. As you can see the from the top chart below, the differencing has removed the seasonal and overall trend from the data. 

From there we can look at the autocorrelation plots to understand which lags are significant in predicting the current traffic. The spikes at lags 1, 7 and 14 suggest thats an the current traffic is heavily correlated to the amount of traffic that was present the day before as well as well as 7 and 14 days prior. This result is intuitive given what we know about the seasonality of the data. 

The residuals from the ARIMA model are shown below. The plot of residual values that reseembales white noise and are normally distributed around zero. This would suggest that there is no trend within the error of the model.  

## Model Comparisons
Both models provide useful predictions for what traffic might look like in the coming months. However, in order to select which model preforms the best we will use cross validation. The results are shown in the table below. The ARIMA model has a lower root mean squared error (RMSE) and mean absolute error (MAE) which means that the values predicted by the ARIMA model are closer to reality. 

# Conclusion
