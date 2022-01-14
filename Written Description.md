# Subway Performance Recommendation for the ★ATRAINZ★
## Background
The ★ATRAINZ★ are the big city's hottest up-and-coming *a capella* group, and have been performing at subway stops to help build a social media following. As a loyal fan from the very beginning, and upon seeing their posts on social media, I have taken it upon myself to find the best subway stops and times of week for them to perform at. This involves performing exploratory data analysis on MTA turnstile data and determining which subway stations have a high density of passengers waiting relative to their train frequency.
## Design
Reaching the largest number of people possible is certainly an important goal of self-promotion. However, to fully appreciate a free musical performance, time spent waiting as passengers is an important value to observe. The goal of this project is to find which subway stops have a high number of passengers as well as a relatively long wait time to find the best potential new fans. 
## Data
MTA turnstile data was used from March 2019-August 2019, featuring hundreds of thousands of entries detailing the time, place, and number of passengers. Additionally, a subway train frequency table was referenced in order to determine how frequently trains visited each station.
## Algorithms
- SQLAlchemy was used to download the data from the website, populate a database, and perform a SQL query on the data
- pass

## Tools
- SQLAlchemy was used to download the data, populate the database, and perform an SQL query
- Pandas was used for most of the data cleaning and manipulation
- Matplotlib was used for the data visualization

## Communication
