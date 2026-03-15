# Rat Sightings in New York City

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Prophet](https://img.shields.io/badge/Prophet-1.1-orange)
![NeuralProphet](https://img.shields.io/badge/NeuralProphet-0.8.0-yellow)
![XGBoost](https://img.shields.io/badge/XGBoost-2.1.4-red)
![statsmodels](https://img.shields.io/badge/statsmodels-0.14.6-teal)
![Optuna](https://img.shields.io/badge/optuna-4.7.0-purple)
![Optuplotlyna](https://img.shields.io/badge/plotly-2.1.1-brown)
![numpy](https://img.shields.io/badge/numpy-1.26.4-black)
![pandas](https://img.shields.io/badge/pandas-2.1.4-white)
![sklearn](https://img.shields.io/badge/sklearn-1.8.0-pink)
![License](https://img.shields.io/badge/License-MIT-green)

---

## Authors

*(Add links to LinkedIn / personal sites later)*

- Krishna Aryal
- Kevin Dao
- Yael Eisenberg
- Ifeoluwa Solomon

---

## Description

The New York City (NYC) rat is considered a cultural symbol of NYC. 
It is estimated that there are about 3 million rats in NYC and in 
recent history, the number of rats has become incredibly problematic. 
Rats spread disease, attack small infants and children, spread waste, 
eat and steal food, and can cause infrastructure damage. However, 
there is some hope as the extended winters due to climate change has 
led to predictions that the extreme cold would cull the rat population. 
Furthermore, the widespread adoption of better trash storage systems 
and better waste management procedures has led to, allegedly, fewer 
rat problems. With recent breakthroughs in tracking rat movement in 
NYC, there is a bit more hope in controlling NYC's rat population. 
In this project, we would like to understand the rat population and 
its movements in NYC. We seek to answer two key questions regarding 
the rat activity in NYC. The main question(s) we found ourselves attempting 
to answer is

**Questions:** Can one predict the future number of rat sightings reported to 311 for each day for the next 14 days at a citywide and borough level? 
How can one improve these predictions by utilizing weather data and various engineered features? How differently do the models perform on each borough?

As part of attempting to answer this question, we found ourselves considering 
rat inspection data, the question of forecasting at the ZIP code level, 
trash collection data, and catch basin data. We did not end up using all of this information
due to time and computational constraints, but these preliminary efforts might be useful
for future endeavors.

---

## Overview

### Boroughs Covered

| Borough | Notebook | Status |
|---------|----------|--------|
| Bronx & Queens | `notebooks/bronx_and_queens/` | Complete |
| Brooklyn | `notebooks/brooklyn/` | Complete |
| Manhattan | `notebooks/manhattan/` | Complete |
| Staten Island | `notebooks/staten_island/` | Complete |
| Citywide | `notebooks/citywide/` | Complete |

---

## Data

The data we gathered comes from NYC Open Data and the IRS. Not all of this data ended up being used for our forecasting purposes, but could be used in future work. There is a [notebook](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/scr/data/download_recent_data.ipynb) which downloads some of this data.

| Dataset | Source | Description |
|---------|--------|-------------|
| Rat Sightings | [NYC Open Data](https://data.cityofnewyork.us/Social-Services/Rat-Sightings/3q43-55fe) | 311 Rat Sightings |
| Rat Inspections | [NYC Open Data](https://data.cityofnewyork.us/Health/Rodent-Inspection/p937-wjvj) | Rat Inspections |
| Catch Basins | [NYC Open Data](https://data.cityofnewyork.us/Environment/Catch-Basin/qxgt-r7dq) | Location of Catch Basins |
| IRS Income Data | [IRS SOI Tax Stats](https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics) | ZIP-Level Income Data |
| DSNY Monthly Tonnage Data | [NYC Open Data](https://data.cityofnewyork.us/City-Government/DSNY-Monthly-Tonnage-Data/ebb7-mvp5/about_data) | Tonnage Data for Waste |
| 2010-2019 311 Reports| [NYC Open Data](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-2019/76ig-c548/about_data) | 311 Reports
Imported as needed | [Open Meteo](https://open-meteo.com/) | Weather Data
---

## Literature

There is an impressive amount of literature focused on understanding 
rat activity in New York City. We highlight some of them since they 
are worth a read. Included also are some recent news articles that 
might be relevant to someone interested in rat sightings in NYC. 
In recent years, NYC has also implemented new sanitation and trash 
rules. Awareness of city policies will and must play a role in our 
modeling efforts.

**Research Papers:**
- [Rat sightings in New York City are associated with neighborhood sociodemographics, housing characteristics, and proximity to open public space](https://doi.org/10.1371/journal.pone.0227057)
- [Computational Urban Ecology of New York City Rats](https://doi.org/10.1371/journal.pone.0227057)

**News Articles:**
- ["If it's cold, they stop mating": New York City rat population may be on the decline](https://www.theguardian.com)
- ["NYC Rats Are Fleeing – for an Incredible 12 Straight Months!"](https://nypost.com)
- [NYC Rat Sightings](https://www.nytimes.com)
- [Official NYC Bin Availability Expands Citywide Ahead of June 2026 Compliance Deadline](https://www.nyc.gov)

---

## Exploratory Data Analysis

For our exploratory data analysis, we focused on trends in rat sightings reports. Initially, we had also considered extra data such as rat inspections, the location of catch basins, income levels in each borough, and trash collection in NYC. Due to limited time, our modeling attempts ended up only using rat sightings data and weather data. For more on our exploratory data analysis and what we observed, see [this notebook](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/notebooks/eda.ipynb).

Our first observation was the seasonality of rat sightings. Every borough experienced increased rat sightings during the months of June, July, and August, and a decrease in rat sightings during the months of November, December, January, and February.

<p align="center">
  <img src="results/eda/dailyratsightings.png" width="1200" alt="Logo" />
</p>

<p align="center">
  <img src="results/eda/dailyratsightingsbyborough.png" width="1200" alt="Logo" />
</p>

One can see this in the cumulative number of rat sightings by month.

<p align="center">
  <img src="results/eda/bymonth.png" width="1500" alt="Logo" />
</p>

It is also known that weather plays a major role in rats abilities to reproduce. We collected the average temperature by day measured 2 meters above the ground in Manhattan. The temperature fluctuations lines up with the number of observed rat sightings per day.

<p align="center">
  <img src="results/eda/weather3.png" width="1200" alt="Logo" />
</p>



The number of rat sightings also exhibited changes in trend. For the years 2020 - 2022, we saw a steady increase in the number of reported rat sightings. One might speculate that this was due to relaxing rules regarding the COVID-19 lockdowns. However, starting in 2023, we saw a steady decrease in rat sightings. Part of this might be explained by renewed efforts by the city to deal with the rat problems e.g. the introduction of new laws regarding trash containiners in 2024. 

<p align="center">
  <img src="results/eda/drsandpolicies.png" width="1500" alt="Logo" />
</p>

<p align="center">
  <img src="results/eda/changeintrend.png" width="1500" alt="Logo" />
</p>

One also has to account for the influence of holidays. 311 rat sightings reports are not jus influenced by ract activity and populations, but also by human behavior. One can see this by looking at a boxplot of rat sightings on holidays versus nonholidays as well as considering the distribution of number of rat sightings each day.

<p align="center">
  <img src="results/eda/holidaysversusnonholidays.png" width="1500" alt="Logo" />
</p>

Even the days leading up to a holiday and the days after a holiday can have an influence on the number of reports.  In the following plot, we considered the average daily sightings in days leading up to a holiday and the days after. In shaded red is a one day window. We see a large dip before a federal holiday and then a large increase in the days that follow. This could partly be explained by human behavior: people do not want to call 311 during a holiday and wait until the days after to make the call. There does not seem to be major influence from the holiday outside a 7 day window before and after a federal holiday.

<p align="center">
  <img src="results/eda/holidaywindows.png" width="1500" alt="Logo" />
</p>

In line with our expectation that human behavior should play a role, we also expected there to be drops in reports on the weekends and Friday. Considering the average daily rat sightings by day of the week, we see that the average on Sundays and Saturdays are about 10 reports while every other day the average is about 12-15.

<p align="center">
  <img src="results/eda/weekaverage.png" width="1500" alt="Logo" />
</p>

Lastly, the number of rat sightings reported in the past can have an influence. We provide ACF and PACF plots of daily rat sightings in NYC. One would expect such influence given that the average rat reproductive cycle ranges from 6-12 weeks. The increase in the ACF as one approaches a lag of 365 is also expected due to the yearly seasonality of the data.

<p align="center">
  <img src="results/eda/acfdailyratsightings.png" width="1500" alt="Logo" />
</p>

<p align="center">
  <img src="results/eda/pacfdailyratsightings.png" width="1500" alt="Logo" />
</p>


## Modeling Approach

We settled on the problem of forecasting the number of rat sightings with a forecast horizon of 14 days. This lines up with biweekly payschedules and lets us ensure that we can (a) capture weekly seasonality in our forecasts and (b) reduce the amount of computations needed to be done in our cross-validation scheme which we will discuss below.

0. Our main choice of **KPI** was to use root mean squared error (RMSE). We chose RMSE to keep the same magnitude since we wanted a sense of "how off was our forecast by day?". We also wanted some sensitivity for large errors as being able to predict the spikes in rat sightings has practical importance. Our choice was also partly motivated by our cross-validation scheme (see 3. below). Since RMSE keeps the same unit as the target, we can take the average of the RMSEs of each day of our fold and get a sense of how well our models performed on each fold.

1. We used the rat sightings data from 2020-01-01 all the way until 2026-02-28 inclusive. At the start of the project, we chose 2026-02-28 as our cutoff date for modeling attempts because there is typically a lag in updating the Open NYC 311 dataset.

2. Because we wish to forecast with 14 day forecast horizons and we have daily data, we chose a walk-forward cross validation scheme of 26 steps and test sizes of 14. Here, the choice to forecast 14 days instead of 7 allows us to instead pick 26 steps to get to 364 days which is almost a full year.

3. We held out the data for 2025-03-01 to 2026-02-28 and did our modeling on the data from 2020-01-01 to 2025-02-28. We chose to hold out a full year since we want to have a full year to evaluate our final models on.

4. As a baseline, we chose the seasonal average model. The data shows strong yearly seasonality so we chose a seasonal average model which looks back 4 years and considers a 4 day window. The performance of this baseline model for each borough and at the citywide level can be found in [this notebook](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/notebooks/baselines.ipynb).

5. We focused mainly on doing daily forecasts. However, considering weekly rat sightings could smooth out the influence of outliers. Initial efforts towards working with weekly data can be found [in this folder](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/tree/main/notebooks/weekly_models). In our exploratory data analysis, we also saw that Staten Island had sparse data and so considering weekly could help. Some initial efforts to do this can be found in this [notebook](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/notebooks/staten_island/4models_staten_island_weekly.ipynb) and this [notebook](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/notebooks/staten_island/5models_statenIsland_prophet_weekly.ipynb).

6. We considered a wide variety of models. Besides the Seasonal Average Model, we also considered using a Year Ago Rolling 4 Week Average which predicts the rolling 4 week average from  last year. More complex modeling tools we tried were: SARIMAX, Prophet, NeuralProphet, XGBoost, Holt-Winters, Year Ago Rolling 4 Week Average. In some cases, we also considered models that combined two or more models such as using Prophet to make the initial forecast and then use XGBoost to improve the forecast by having XGBoost try to predict the residuals. In the case of modeling for Queens and Bronx, we tried Ridge Regression and an Ensemble Model which took the average of Prophet, Ridge Regression, XGBoost, and SARIMA.


7. *Why Prophet?* As we understand it, Prophet uses a [decomposition of time series](https://en.wikipedia.org/wiki/Decomposition_of_time_series) but has features that appeared relevant to our situation. For example, Prophet is able to account for [holidays and special events](https://facebook.github.io/prophet/docs/seasonality,_holiday_effects,_and_regressors.html#modeling-holidays-and-special-events), for multiple seasonalities at once such as weekly and yearly seasonality, and for [changes in trend](https://facebook.github.io/prophet/docs/trend_changepoints.html).



For more details on our modeling approach, please refer [here](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/notebooks/evaluation_plan.md).


## Setting Up and Notes

1. Go to the [notebooks/package_installs.ipny](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/notebooks/package_installs.ipynb) notebook and run it to download the necessary packages.

2. Go to [scr/data/download_recent_data.ipynb](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/scr/data/download_recent_data.ipynb) and run the notebook to download the most recent data off the web.

3. If one is seeking just the two week forecast of rat sightings, go to [notebooks/forecast.ipynb](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/notebooks/forecast.ipynb) and run the whole notebook. Then, scroll to the bottom of the notebook for the forecasts. Note that due to computational complexity and runtime, we have not chosen to use the "best model" (i.e. models with the lowest RMSEs following our evaluation method) in this notebook.

## Modeling Results and Further Work

A detailed description of the results of our modeling work and for more on further work that might be done, please refer to [results/summary.md](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/results/summary.md) and [results/furtherwork.md](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/blob/main/results/furtherwork.md).

## Directory

