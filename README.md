# Surfs_up
We are using SQLite, SQLAlchemy, and Flask to build on knowledge of SQL database structures and querying methods.

Project Overview

To open a Surf’n’Shake shop, this shop sells surf boards and ice cream in Oahu, Hawaii, the weather must be favourable most days of a year. A perfect spot for the shop is a place with the right balance of warm temperatures, sunny days throughout the year and just enough rain to keep the vegetation green. Once these criterias are met, we can be very confident that new shop will rise, shineand be a success.

Purpose

To ensure that we will choose the right spot for shop, we will make some data-driven decisions. This analysis will focus on the temperature and (precipitation) rainfall for the past 7 years from 2010 to 2017, specifically for June and December, the two months that are far apart to ensure that we have a good condition year-round.

Requirements

Temperature analysis for June and December from 2010 to 2017.

Resources

Data Source: - hawaii.sqlite

Environment: - Python 3.7

Dependencies:

import pandas as pd
import numpy as np
import datetime as dt
import matplotlib
from matplotlib import style
style.use('fivethirtyeight')
import matplotlib.pyplot as plt
Python SQL toolkit and Object Relational Mapper:

import sqlalchemy
from sqlalchemy.ext.automap import automap_base
from sqlalchemy.orm import Session
from sqlalchemy import create_engine, func
Software:

Jupyter Notebook
SQLite("A popular database engine, a version of SQL, that is stored locally and supports quick testing and easy prototyping")
SQLAlchemy("A query tool design for SQLite to query SQLite databases")
Result

This analysis focuses on the temperature and rainfall from six different weather stations on Oahu, Hawaii from 2010 to 2017 for June and December.

Comparison of the Temperatures for June and December

1. Total Number of data

There's less data for December (1517 data points) than for June (1700 data points).

2. STATISTICS of the data
![Screen Shot 2022-01-30 at 1 24 44 AM](https://user-images.githubusercontent.com/91812090/151690720-bb705ed3-90eb-4245-9314-491acd10dab0.png)


Temperatures are more spread out in December (std = 3.7) than in June (std = 3.3).
June’s mean and median are 74.94 °F and 75.00 °F respectively.
December’s mean and median are 71.04 °F and 71.0 °F respectively.
Maximum temperature in December is 83 °F and in June 85 °F.
Minimum temperature in December is 56 °F and in June 64 °F.
3. Quartiles

1st quartile: 25% of all data is below 69 °F in December and 73 °F in June.
3rd quartile 75% of all data is below 74 °F in December and 77 °F in June.


Measures of Central Tendency of Temperatures for December and June in Oahu, Hawaii.

In addition Precipitation(Rainfall) analysis for June and December from 2010 to 2017.

![June_Prcp](https://user-images.githubusercontent.com/91812090/151690757-c9fcac8a-3c7d-4500-9728-b32ef4e4a171.png)

![Dec_Prcp](https://user-images.githubusercontent.com/91812090/151690770-2338f714-2563-424d-a37c-b0f1741cfdc3.png)

Comparison of the Precipitation for June and December

1. Total Number of data

There are less data for December (1405 data points) than for June (1574 data points).
2. STATISTICS of the data

Precipitation quantity is more spread out in December (std = 0.5) than in June (std = 0.33).
June’s mean and median are 0.13 inches and 0.02 inches respectively.
December’s mean and median are 0.21 inches and 0.03 inches respectively.
Maximum Precipitation in December is 6.42 inches and 4.43 inches in June.
Minimum Precipitation in December is 0 inches and 0 inches in June.
3. Quartiles

1st quartile: 25% of all data is at 0 inches in December and 0 inches in June.
3rd quartile 75% of all data is below 0.15 inches in December and 0.12 inches in June.


Measures of Central Tendency of Precipitation for December and June in Oahu, Hawaii.

Summary

Descriptive statistics provides fast results and tells us the weather story about the area. For more explanations some additional analysis is provided by myself.

Temperatures for June and December
![June_Temps](https://user-images.githubusercontent.com/91812090/151690811-afa9feb6-681e-4489-aba2-d237d25f19c5.png)
![December_Temps](https://user-images.githubusercontent.com/91812090/151690823-c3d2f19c-59cf-4983-86f2-68c6c8fb758e.png)

From the temperature report we can see that there is not much difference in the weather in June and December, this indicated steady and mild temperatures year round. Mean, median and 2nd quartile data are closely together. It means that distribution of the data is not spread out. For information about protentional outliers and other trends we will plot the box and whiskers chart.

![Screen Shot 2022-01-30 at 1 32 27 AM](https://user-images.githubusercontent.com/91812090/151690923-7def7869-4a6f-4e83-9fef-fa49c3fdde21.png)


Box and Whiskers Plot of Temperatures for December and June in Oahu, Hawaii.

From the graph we can see that there are several outliers. There are more outliers below the lower boundary in December, however the minimum temperature is 56 °F.

Calc Funcion

Function calc_temps that will accept start date and end date in the format '%Y-%m-%d' and return the minimum, average, and maximum temperatures for that range of dates'2010-01-01'- '2017-30-12'

Design a query to retrieve the of Average tobs data and plot the results.

To see the difference year to year I have provided another graph of Average temprature grouped by year.

![Screen Shot 2022-01-30 at 1 37 42 AM](https://user-images.githubusercontent.com/91812090/151690999-fb88e76a-2ab7-46b3-a867-4b2490e11839.png)


Average Temperatures in between year 2010 and year 2017 in Oahu, Hawaii.

Precipitation for June and December
![June_Prcp](https://user-images.githubusercontent.com/91812090/151691016-90d046ae-229b-4b60-8d82-6cf21c61c9c7.png)
![Dec_Prcp](https://user-images.githubusercontent.com/91812090/151691021-bf11148b-ae2b-4aa9-81ac-3685de04e07a.png)

What we notice is the max prcp in June and December (4.43 and 6.42 inches). Also in both cases, is highly above the mean. Standard deviation is also high. The mean, median or 2nd quartile are far apart. We understand distribution of the data is vastly spread out and indicates the presence of extreme values in the dataset. The easiest way to determine outliers is to plot box and whiskers chart.

![Precipitation Data (2010-2017)](https://user-images.githubusercontent.com/91812090/151691311-915d1daf-8231-42c1-a536-fe7ea504bf50.png)


Box and Whiskers Plot of Precipitation for December and June in Oahu, Hawaii.

There are 183 outliers in June and 205 outliers in December.
It is enough power to impact the mean, yet 183 and 205 data points out of 1574 and 1405 respectively is not that much.
That indicates isolated extreme rainfall as in precipitation.
This analysis capture weather data for 7 years from 2010 to 2017.
