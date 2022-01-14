# Subway Performance Recommendation for the ★ATRAINZ★
## Background
The ★ATRAINZ★ are the big city's hottest up-and-coming *a capella* group, and have been performing at subway stops to help build a social media following. As a loyal fan from the very beginning, and upon seeing their posts on social media, I have taken it upon myself to find the best subway stops and times of week for them to perform at. This involves performing exploratory data analysis on MTA turnstile data and determining which subway stations have a high density of passengers waiting relative to their train frequency.
## Design
Reaching the largest number of people possible is certainly an important goal of self-promotion. However, to fully appreciate a free musical performance, time spent waiting as passengers is an important value to observe. The goal of this project is to find which subway stops have a high number of passengers as well as a relatively long wait time to find the best potential new fans. 
## Data
MTA turnstile data was used from the spring and summer of 2019, featuring hundreds of thousands of entries detailing the time, place, and number of passengers. Additionally, a subway train frequency table was referenced in order to determine how frequently trains visited each station.
## Algorithms
- SQLAlchemy statement including WHERE, AND, UNION, and LIKE to read in from a database
- Pandas tools to clean, aggregate, and explore the data
- Pandas tools apply() and map() to modify big series in a non-uniform manner
- Defining Python methods to calculate the frequency of trains given a timetable and window of time

The amount of traffic for each entry was determined by taking the difference between two adjacent entries' counter for each turnstile, then deleting each entry that had no previous entry to reference. The absolute value was used in order to account for turnstiles that were counting backward. Despite this, there were still some anomalies, and a histogram of the number of entries across the entire database showed that values greater than 10^3.7 were statistical outliers and likely the result of some error.

This project made use of datetime objects, using the pandas groupby method in order to aggregate data taken from the same time from week to week. Datetime was also used to indentify the day of week for each entry, using the pandas map() method with a dictionary to set the weekday() function output to something more readable.

The most difficult part of the project was determining the number of trains that entered each station for the recorded interval, as each line has a different frequency depending on time of day, unique to each individual line. This was determined by taking the timestamp of the entry, counting the timedelta between the entry and the most recent schedule change, then using that timedelta with the lines serviced by the station to reference the frequency table. This was repeated until the full four-hour span of the entry was accounted for. This method was then applied to the series as a whole with apply().

## Tools
- SQLAlchemy was used to download the data, populate the database, and perform an SQL query
- Pandas was used for most of the data cleaning and manipulation
- DateTime was used to determine the number of trains for each period, as well as group the entries to spot weekly trends
- Matplotlib was used for the data visualization
- The NumPy function for log10 was used along matplotlib visualization to help identify outliers

## Communication
Recommendations for which stations to perform at are highlighted in a slide presentation. The presentation goes over the design, data, and algorithms of the project. It also provides actionable recommendations with locations and varied times of day and week based on the data processed during this project.
