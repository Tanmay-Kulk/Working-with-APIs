# Working-with-APIs

The idea behind creating this repository is to share a small program that I've done using an API and conducted some analysis.

### About APIs <br/>
Think of APIs (short form for Application Programming Interfaces) as messengers that help different computer programs talk to each other. Just like how you might ask a waiter to bring you food from the kitchen, APIs let your code ask other services for data and get it delivered back to you. For data analysis, APIs are incredibly useful because they give you access to fresh, real-time information without having to collect it yourself. Instead of manually gathering data from websites or databases, you can simply ask an API for what you need. Here's how it works: your program sends a request (like "give me today's flight information"), and the API responds with the data you asked for, usually in a format called JSON that computers can easily understand. This means you can always work with the most up-to-date information available.


### Project Overview <br/>
This project demonstrates how to work with flight data APIs (in this case) to extract, process, and analyze real-time flight information. Using the AeroDataBox API through RapidAPI, we fetch comprehensive flight data from Toronto Pearson International Airport (YYZ) and perform exploratory data analysis. The analysis focuses on understanding flight patterns, airline performance, delay statistics, and operational insights that could be valuable for airport management, travelers, or aviation enthusiasts.

### Working of Code <br/>
#### Data Integration and Setting up the environment for API integration <br/>
The code starts by loading your API key from a CSV file - think of this like keeping your house key in a secure place rather than leaving it lying around. Then it asks the AeroDataBox API for flight data, specifying exactly what we want: which time period to look at, what types of flights to include, and how much detail we need. The API sends back a huge pile of flight information, everything from when flights are supposed to leave and arrive, which airlines they belong to, what type of planes they're using, and their schedules. This information comes in a format called JSON. So we convert it into a neat, organized table (DataFrame) that's much easier to work with.

#### Data Cleaning and Pre-processing <br/>
Real-time data can be messy at times, think of it like how some forms you fill out might have blank fields or incomplete information. This code tackles this by checking each column to see how much information is missing. If a column is missing more than 90% of its data, we throw it out since it's not useful for analysis. We also fix the date and time information so that we can properly understand when flights are scheduled. Think of it like converting "5 PM" into a format that lets us calculate how long flights take or figure out delays. The code also creates some new pieces of information in the form of new columns in the dataframe, like calculating exactly how long each flight should take, whether flights are running late, and what hour of the day flights typically depart.

#### Exploratory Analysis <br/>
This section provides insights into flight operations through multiple perspectives. It examines airline performance by counting flights per carrier and calculating average delays, helping identify the most active airlines and their punctuality records. Delay analysis focuses on understanding timing patterns, calculating on-time performance metrics, and visualizing delay distributions. The code defines flights within 15 minutes of scheduled time as "on-time," providing practical performance indicators. Airport and aircraft analysis reveal popular destinations from Toronto Pearson Airport and commonly used aircraft models, offering insights into route preferences and fleet composition. The hourly pattern analysis shows peak travel times throughout the day.


### Bonus <br/>
In the end, this file of code also provides you with an example that if you only require the arrival data, how you can get and in that, I have labeled the steps you can follow to achieve the same with other parameters as well!









