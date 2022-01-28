# Surfs_up
We are using SQLite, SQLAlchemy, and Flask to build on knowledge of SQL database structures and querying methods.
Project Overview

To open a Surf’n’Shake shop, a shop that sells surf boards and ice cream in Oahu, Hawaii, the weather must be in our favor most days of a year. A perfect spot for the shop is a place with the right balance of warm temperatures, sunny days throughout the year and just enough rain to keep the vegetation green. If those criteria are met, we can be confident that new shop will rise and shine.

Purpose

To ensure that we will choose the right spot for shop, we want to make some data-driven decisions; therefore, this analysis focuses on the temperature and precipitation(rainfall) for the past 7 years from 2010 to 2017, specifically for June and December, the two months that are apart enough to ensure that we have a good condition year-round.

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

The analysis focuses on the temperature and rainfall from six different weather stations on Oahu, Hawaii from 2010 to 2017 for June and December specifically.

Comparison of the Temperatures for June and December

1. Total Number of data

There are less data for December (1517 data points) than for June (1700 data points).
2. STATISTICS of the data

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

Above descriptive statistics provides quick results and tell us weather story about the area. For more explanations some additional analysis is provided by me.

Temperatures for June and December

From the temperature report we can see that there is not much difference in the weather in June and December, indicating mild and steady temperatures year-round. Mean, median and 2nd quartile data are closely together. It means that distribution of the data is not spread out. For information about protentional outliers and other trends we will plot the box and whiskers chart.



Box and Whiskers Plot of Temperatures for December and June in Oahu, Hawaii.

From the graph we can see that there are just a few outliers. There are more outliers below the lower boundary in December, however the minimum temperature is 56 °F.

Calc Funcion

Function calc_temps that will accept start date and end date in the format '%Y-%m-%d' and return the minimum, average, and maximum temperatures for that range of dates'2010-01-01'- '2017-30-12'

Design a query to retrieve the of Average tobs data and plot the results.

To see the difference year to year I have provided another graph of Average temprature grouped by year.



Average Temperatures in between year 2010 and year 2017 in Oahu, Hawaii.

Precipitation for June and December

The first difference that we notice is the max prcp in June and December (4.43 and 6.42 inches respectively) and in both cases, which is highly above the mean. Standard deviation is also high. And mean, median or 2nd quartile are far apart. Here we understood distribution of the data is highly spread out and indicates the presence of extreme values in the dataset. The easiest way to determine outliers is to plot box and whiskers chart.



Box and Whiskers Plot of Precipitation for December and June in Oahu, Hawaii.

There are 183 outliers in June and 205 outliers in December.
It is enough power to impact the mean, yet 183 and 205 data points out of 1574 and 1405 respectively is not that much.
That indicates isolated extreme rainfall as in precipitation.
This analysis capture weather data for 7 years from 2010 to 2017.
