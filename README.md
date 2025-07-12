# Working-with-APIs

The idea behind creating this repository is to share a small program that I've done using an API and conducted some analysis.

### Project Motivation <br/>
I have used RapidAPI to work on this project. It is a good resource to learn about different kinds of available APIs; through this, you can get access to over 7-8 categories of APIs, including Travel, Cybersecurity, and many more. Being a planespotter, I picked up an API related to aviation that included data related to arrivals, departures, flight name, arrival airport, and many more that piqued my interest. To start things off, we got the responses in the form of a JSON file. The idea that I had in my mind was to turn this JSON output into a dataframe and then clean that dataframe and perform some analysis. 


### Response generated from an API <br/>
To give a quick glimpse of the output, this is how it looked. 

<img width="1353" height="348" alt="image" src="https://github.com/user-attachments/assets/1433c8d1-8d1e-44b7-a411-3c07f3287908" />

This is a type of nested dictionary where 'departures' is the key and the rest are records or values. An interesting thing about these records or values is that if you look closely, you see that 'departure' is a key and has values like scheduledTime, revisedTime etc., followed by 'arrival', 'airport etc.

<img width="867" height="450" alt="image" src="https://github.com/user-attachments/assets/6bee993a-8342-4ff3-91c0-58be2b05a368" />

I've tried showing how it works in the above diagram, but if it's not clear, then to give a gist of it, the value is in the form of a list, and in each list, there is a dictionary which has key like 'departure', 'arrival', 'airport' etc. and those keys have values which are again in the form of a key-value pair making it a nested dictionary.

### Analysis Procedure <br/>
To begin our analysis, I used the get function to fetch the 'departures' data, and then with the help of *pandas.json_normalize()*, I transformed this JSON output into a pandas dataframe. Followed by understanding the shape and data types of the columns in the dataframe. The data that I gathered had missing values, which I dealt with the help of a function that helped me eliminate the columns where more than 90% of their data was missing, which meant that those columns wouldn't be very useful. 

<img width="426" height="202" alt="image" src="https://github.com/user-attachments/assets/4f0f9471-cc2a-4f40-9616-723f4137f7d4" />

The above image shows an output from the function that I ran.

Now, after dealing with missing values, I changed the datatype of the columns that had date and time to the "datetime" datatype in Python. Then, performed some basic cleaning steps where I cleaned the column names and added a few columns that represented flight duration, delays for both the departure and arrival periods, Furthermore, I also added a column that extracted the hour from those columns that included "Time" in them. 

### Four Types of Analysis <br/>
I carried out 4 types of analysis with the available data, which tells us about the airline performances, delays in both departure and arrival, the top airports which had the highest traffic, and which aircraft model was most frequently used.








