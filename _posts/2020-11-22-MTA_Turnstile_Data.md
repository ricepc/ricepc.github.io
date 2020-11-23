---
layout: post
title: Predicting Subway Usage in the Covid-19 Era
cover-img: /assets/img/PennStat.png
#thumbnail-img: /assets/img/thumb.png
#share-img: /assets/img/path.jpg
tags: [Forecasting, R, Python]
---

# Summary:
The Covid-19 pandemic has presented many industries with an interesting problem, Is it possible to model customer actions as they begin to adjust to the new normal? Using Data provided by New York's Metropolitan Transportation Authority, I was able to create a reliable firecast. 

# Retrieving and Cleaning the Data
All data for this project can be found on Metropolitan Transportation Authority's (MTA) [website](http://web.mta.info/developers/turnstile.html) or on [my github page.](https://github.com/ricepc/MTA_Turnstile_Data) 

Each week the MTA posts a txt file with the daily number of entries and exits from all New York subway stations. My goal in this analysis was to focus on only the data from Penn Station to better understand what patterns exist in the data and how they may be used to predict future ridership as New Yorkers begin to adjust to the new normal.

# Visualizing the Data

![Time Series Data](https://github.com/ricepc/ricepc.github.io/raw/master/assets/Turnstile%20_Images/Full_TS_AutoPlot.JPG)

![Covid Time Series Data](https://github.com/ricepc/ricepc.github.io/raw/master/assets/Turnstile%20_Images/Covid_TS_Autoplot.jpeg)

![Covid ggseason](https://github.com/ricepc/ricepc.github.io/raw/master/assets/Turnstile%20_Images/Covid_ggseason.png)

![Covid ssubseries](https://github.com/ricepc/ricepc.github.io/raw/master/assets/Turnstile%20_Images/covid_ggsubseries.png)

![Covid Decomp](https://github.com/ricepc/ricepc.github.io/raw/master/assets/Turnstile%20_Images/STL_Decomp.png)

# Forecast Models

# Conclusion
