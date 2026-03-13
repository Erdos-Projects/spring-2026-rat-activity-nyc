# Rat Sightings in New York City

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Prophet](https://img.shields.io/badge/Prophet-1.1-orange)
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
the rat activity in NYC. The main question we found ourselves attempting 
to answer is

**Question:** > Can one predict the future number of rat sightings reported to
> 311 for each day for the next 14 days at a citywide and borough level?

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
| Bronx & Queens | `notebooks/bronx_and_queens/` | ✅ Complete |
| Brooklyn | `notebooks/brooklyn/` | ✅ Complete |
| Manhattan | `notebooks/manhattan/` | ✅ Complete |
| Staten Island | `notebooks/staten_island/` | ✅ Complete |
| Citywide | `notebooks/citywide/` | ✅ Complete |

---

## Data

The data we gathered comes from NYC Open Data and the IRS.

| Dataset | Source | Description |
|---------|--------|-------------|
| Rat Sightings | [NYC Open Data](https://data.cityofnewyork.us/Social-Services/Rat-Sightings/3q43-55fe) | 311 Rat Sightings |
| Rat Inspections | [NYC Open Data](https://data.cityofnewyork.us/Health/Rodent-Inspection/p937-wjvj) | Rat Inspections |
| Catch Basins | [NYC Open Data](https://data.cityofnewyork.us/Environment/Catch-Basin/qxgt-r7dq) | Location of Catch Basins |
| IRS Income Data | [IRS SOI Tax Stats](https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics) | ZIP-Level Income data |
| Waste Data | [NYC OPen](https://github.com/Erdos-Projects/spring-2026-rat-activity-nyc/settings) | NYC Wast Collection Data |
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

--

## Setup Instructions
