# 🐀 Rats in New York City

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Prophet](https://img.shields.io/badge/Prophet-1.1-orange)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 👥 Authors

*(Add links to LinkedIn / personal sites later)*

- Krishna Aryal
- Kevin Dao
- Yael Eisenberg
- Ifeoluwa Solomon

---

## 📋 Description

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
the rat activity in NYC.

**Question 1:**
> Can one predict the future number of rat sightings in a given 
> location by using the features: time, past data on rat sightings, 
> past data on rat inspections, proximity to key landmarks such as 
> restaurants, income status in the area, and the type of building 
> we are considering?

**Question 2:**
> Using the rat sightings data and some of the features considered 
> above, can we predict the likelihood that the result of a rat 
> inspection is a "Fail"?

---

## 🗺️ Overview

### Boroughs Covered

| Borough | Notebook | Status |
|---------|----------|--------|
| Bronx & Queens | `notebooks/Bronx_and_Queens/` | ✅ Complete |
| Brooklyn | `notebooks/brooklyn/` | ✅ Complete |
| Manhattan | `notebooks/manhattan/` | ✅ Complete |
| Staten Island | `notebooks/staten_island/` | ✅ Complete |
| Citywide | `notebooks/citywide/` | ✅ Complete |

---

## 📊 Data

Our data for this project comes from NYC Open Data and the IRS.

| Dataset | Source | Description |
|---------|--------|-------------|
| Rat Sightings | [NYC Open Data](https://data.cityofnewyork.us/Social-Services/Rat-Sightings/3q43-55fe) | 311 rat complaint records |
| Rat Inspections | [NYC Open Data](https://data.cityofnewyork.us/Health/Rodent-Inspection/p937-wjvj) | Health dept inspection results |
| Catch Basins | [NYC Open Data](https://data.cityofnewyork.us/Environment/Catch-Basin/qxgt-r7dq) | Location of catch basins |
| IRS Income Data | [IRS SOI Tax Stats](https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics) | ZIP-level income distribution |

---

## 📚 Literature

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

## ⚙️ Setup Instructions

### Prerequisites

1. Python 3.10 or higher
2. Git LFS — required for large data files

### Step 1 — Install Git LFS

Large data files are stored using Git LFS.
Install it before cloning:

```bash
# Windows — download installer from
# https://git-lfs.com

# Mac
brew install git-lfs

# Linux
sudo apt install git-lfs