# Subway Performance Recommendation for the ★ATRAINZ★
## Background
The ★ATRAINZ★ are the big city's hottest up-and-coming *a capella* group, and have been performing at subway stops to help build a social media following. As a loyal fan from the very beginning, and upon seeing their posts on social media, I have taken it upon myself to find the best subway stops and times of week for them to perform at. This involves performing exploratory data analysis on MTA turnstile data and determining which subway stations have a high density of passengers waiting relative to their train frequency.
## Design
Reaching the largest number of people possible is certainly an important goal of self-promotion. However, to fully appreciate a free musical performance, time spent waiting as passengers is an important value to observe. The goal of this project is to find which subway stops have a high number of passengers as well as a relatively long wait time to find the best potential new fans. 
## Data
MTA turnstile data was used from March 2019-August 2019, featuring hundreds of thousands of entries detailing the time, place, and number of passengers. Additionally, a subway train frequency table was referenced in order to determine how frequently trains visited each station.
## Algorithms
- SQLAlchemy statement including WHERE, AND, UNION, and LIKE
- something
The amount of traffic for each entry was determined by taking the difference between two adjacent entries' counter for each turnstile, then deleting each entry that had no previous entry to reference. The absolute value was used in order to account for turnstiles that were counting backward. Despite this, there were still some anomalies, and a histogram of the number of entries across the entire database showed that values greater than 10^3.7 were statistical outliers and likely the result of some error.

The most difficult part of the project was determining the number of trains that entered each station for the recorded interval, as each line has a different frequency depending on time of day, unique to each individual line. This was determined by taking the timestamp of the entry, counting the timedelta between the entry and the most recent schedule change, then using that timedelta with the lines serviced by the station to reference the frequency table. This was repeated until the full four-hour span of the entry was accounted for.

## Tools
- SQLAlchemy was used to download the data, populate the database, and perform an SQL query
- Pandas was used for most of the data cleaning and manipulation
- DateTime was used to determine the number of trains for each period, as well as group the entries to spot weekly trends
- Matplotlib was used for the data visualization

## Communication
