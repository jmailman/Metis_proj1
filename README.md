# Project 1: Women Tech Women Yes! (WTWY) Exploratory Data Analysis


# Description
<p>Karrine and Dahlia from WTWY International have tasked us with using New York City's Metropolitan Transportation Authority subway data to help optimize the placement of their street teams. Their objective is to gather the most signatures, with a preference to target those who will attend their annual summer gala and contribute to their cause.</p>

# Target Variables
- Total number of entries and exits at stations
- Time of day of maximum pedestrian traffic
- Day of the week of maximum pedestrian traffic
- Median income of station locations


# Data Used
- [MTA Turnstile Data](http://web.mta.info/developers/turnstile.html)
- [MTA Stations](http://web.mta.info/developers/data/nyct/subway/Stations.csv)
- [MTA Turnstiles Remote-Complex Lookup](https://qri.cloud/nyc-transit-data/remote_complex_lookup)
- [uszipcode](https://uszipcode.readthedocs.io/index.html)

# Tools Used
- Python
- Numpy
- Pandas
- Matplotlib
- Seaborn
- uszipcode
- datetime
- geopandas

# Analysis strategies and results
1. We considered the overall distribution of subway turnstile traffic throughout the city and notice that most of the traffic does not occur at the most trafficked stations
2. We examined the subway turnstile traffic on different days of the week and conclude that Monday through Wednesday are the most active
3. We wanted to consider how subway turnstile traffic varies by time of day/night so we looked at all six four-hour time intervals provided in the MTA's turnstile dataset. To analyze this data, we deployed primarily two types of visualizations: 1. time-series scatterplots of traffic at every turnstile, with the graph adjusted to use thin horizontal colored strips rather than tiny colored points. (The strips have more visual presence without occluding each other as much as comparably sized dots); 2. time-series scatterplots of the aggregated mean (average) amount of turnstile traffic during each four-hour period. From these visualizations, we noticed an intriguing pattern: Unlike the peak turnstile traffic during morning and afternoon/evening rush hours at the busiest subway stations, turnstile traffic at NYC stations overall instead peaks in the late-evening hours between 8pm and midnight (often with a lesser peak in the early afternoon). This pattern holds true for the specific stations we analyzed as well.
4. To consider turnstile traffic of people working in the technology sector, we looked at the time-of-day/night and day-of-the-week data for the subway station located at the Flatiron building (23rd st at Broadway and 5th Ave) and the three nearest stations.
5. We wanted to consider which stations are situated in high-income neighborhoods. This involved joining (merging) the turnstile data with income data from the uszipcodes dataset. To visualize this connection, we used initially generated scatterplots based on latitude and longitude, coloring points by income level and and sizing them by their amount of turnstile traffic. (We later improved the visualization by superimposing the scatterplots onto a map, using geopandas.) We found that the stations in the highest-income neighborhoods are _not_ those with greatest amount of turnstile traffic overall. This analysis enabled us to additionally examine the times of highest traffic at the three highest-income neighborhoods: World Trade Center, Lincoln Center, and Park Place.


# Recommendations
Rather than identifying places with the most through-traffic overall (which may include a high proportion of tourists and suburban commuters) we prioritized the preference to target those who will attend this technology-themed gala and contribute to the cause.  Therefore we sought to develop recommendations that most strategically reach people interested or involved in technology and people with the means to donate generously. We developed two primary time-and-place recommendations with the option to extend to five additional stations, also suggested by the analysis.
1. **Flatiron** station (23rd and Broadway) **8pm to midnight**, on **Monday, Tuesday, and Wednesday**. (The focus could extend to the three other stations in the area: Gramercy, 23rd and 6th Ave, and Union Square)
2. **Lincoln Center** station (66th and Broadway) **12 noon to midnight**, on **Monday – Thursday**. (The focus could also extend to two of the other highest-income neighborhoods: World Trade Center and Park Place.)
