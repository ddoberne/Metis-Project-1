# Metis Project 1: Exploratory Data Analysis
## Background:
The ★ATRAINZ★ are a new *a capella* group out of Brooklyn, and as part of an initiative to build their social media following, have begun looking at areas where they perform in public to garner attention. As a diehard fan of the group since its inception, I've decided to run some data analysis to help their performances reach as many potential new followers as possible.
## Question/need:
### What is the framing question of your analysis, or the purpose of the model/system you plan to build?
At which stations in the MTA transit system and what time of day are the greatest number of people waiting for the longest time to be willing to take in and appreciate a musical performance?
### Who benefits from exploring this question or building this model/system?
The ★ATRAINZ★, or any other group or individual that is looking to have a captive audience, willing or otherwise.
## Data Description:
### What dataset(s) do you plan to use, and how will you obtain the data?
- Turnstile data from the MTA website, containing the entries and exits for each station separated in 4 hour increments. 3 months' worth of data will be used to create a sufficiently large sample.
- Subway schedule data from the MTA website, detailing the frequency of subway trains at different periods of the day.
Turnstile data is available as .csv files, and the frequency table exists as a spreadsheet.
### What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?
Number of entries from the turnstiles at a specific station is the data will be what I am looking for. Time between trains for each line depending on time of day is also necessary for analysis.
### If modeling, what will you predict as your target?
My aim is to disply the stations with the best ratios of traffic to time waiting. I will be looking for stations where there are a high number of entries per time between trains.  Exits per time and raw entries will also be observed, though as secondary observations.
## Tools:
### How do you intend to meet the tools requirement of the project?
SQLAlchemy will be used to pull the data sets and populate the database. Two tables will be created, so a join will be necessary. A SQL query will be used to pull the data into a pandas dataframe. Pandas will be used to gain the insights I am looking for. Finally, matplotlib will be used to present the data in a clear way.
### Are you planning in advance to need or use additional tools beyond those required?
I do not plan to, though as I get further in my project that may change.
## MVP Goal:
### What would a minimum viable product look like for this project?
An MVP would be able to show which stations along a single line would make the best performance venues based on the amount of traffic there and how long those passengers have to wait before boarding their train, and what time of day optimizes that value.
