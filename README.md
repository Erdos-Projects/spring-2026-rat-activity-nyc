# Rats in New York City

## Authors

(Add links to linkedin / personal sites later)

* Krishna Aryal
* Kevin Dao
* Yael Eisenberg
* Ifeoluwa Solomon

## Description

The New York City (NYC) rat is considered a cultural symbol of NYC. It is estimated that there are about 3 million rats in NYC and in recent history, the number of rats has become [incredibly problematic](#https://phys.org/news/2025-08-york-declares-total-war-prolific.html). Rats spread disease, attack small infants and children, spread waste, eat and steal food, and can cause infrstructure damage. However, there is [some hope](#https://www.nytimes.com/2026/02/11/nyregion/rats-nyc-snow-cold.html) as the extended winters due to climate change has lead to predictions that the extreme cold would cull the rat population. Furthermore, the widespread adoption of better trash storage systems and better waste management procedures has lead to, allegedly, fewer rat problems. With recent [breakthroughs in tracking rat movement in NYC](#https://www.newyorker.com/science/elements/is-the-rat-war-over), there is a bit more hope in controlling NYC's rat population.

In this project, we would like to understand the rat population and its movements in NYC. We seek to answer two key questions regarding the rat activity in NYC.

* Can one predict the future number of rat sightings in a given location by using the features: time, past data on rat sightings, past data on rat inspections, proximity to key landmarks such as restaurants, income status in the area, and the type of building we are considering?

* Using the rat sightings data and some of the features considered above, can we predict the likelihood that a the result of a rat inspection is a "Fail"?


### Overview

###  Data

Our data for this project comes from NYC Open Data and the IRS.

* [NYC Open Data Rat Sightings](https://data.cityofnewyork.us/Social-Services/Rat-Sightings/3q43-55fe/about_data) 
* [NYC Open Data on Rat Inspections](https://data.cityofnewyork.us/Health/Rodent-Inspection/p937-wjvj/about_data) 
* [NYC Open Data on Location of Catch Basins](https://data.cityofnewyork.us/Environment/NYCDEP-Citywide-Catch-Basins/2c5m-rke8)
* [IRS SOI Tax Stats](https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics-zip-code-data-soi)

### Literature

There is an impressive amount of literature focused on understanding rat activity in New York City. We highlight some of them since they are worth a read. Included also are some recent news articles that are might be relevant to someone interested in rat sightings in NYC. In recent years, NYC has also implemented [new sanitation and trash rules](https://portal.311.nyc.gov/article/?kanumber=KA-02086). Awareness of city policies will and must play a role in our modeling efforts.

* [Rat sightings in New York City are associated with neighborhood sociodemographics, housing characteristics, and proximity to open public space](https://pmc.ncbi.nlm.nih.gov/articles/PMC4157232/)
* [Computational Urban Ecology of New York City Rats](https://pmc.ncbi.nlm.nih.gov/articles/PMC12330660/)
* ["If it’s cold, they stop mating": New York City rat population may be on the decline](https://www.theguardian.com/us-news/2026/feb/28/new-york-city-rat-population-decline)
* ["NYC Rats Are Fleeing – for an Incredible 12 Straight Months!"](https://www.nyc.gov/site/dsny/news/25-039/nyc-rats-fleeing-an-incredible-12-straight-months-#/0)
* [NYC Rat Sightings](https://kaityb24.github.io/RatSightings/)
* [Official NYC Bin Availability Expands Citywide Ahead of June 2026 Compliance Deadline](https://www.nyc.gov/site/dsny/news/26-016/official-nyc-bin-availability-expands-citywide-ahead-june-2026-compliance-deadline)

### Instructions


1. Go to scr/data/download_recent_data.ipynb and run the notebook to download the recent data from NYC Open data.

2. Go to the folder scr/cleaning and run the three notebooks found there to clean the data that has just been downloaded.

3. After this, one can go to the notebooks/eda.ipynb and run the whole notebook.


### To-Do List

1. Need to remove data that is not used later e.g. catch_basin, and IRS data.
2. Need to remove notebooks that are no longer relevant.
3. Probably should make separate notebooks for data stored at various ranges (location size long+lat range / ZIP / borough /citywide, daily/weekly/monthly data size considered).
