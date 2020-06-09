## Objective
The objective of this project is to analyze and select the best locations in the city of Mumbai, India to open a new shopping mall. Using data science methodology and machine learning techniques like clustering, this project aims to provide solutions to answer the business question: In the city of Mumbai, India if a property developer is looking to open a new shopping mall, where would you recommend that they open it?

## Data
To solve the problem, we will need the following data:
- List of neighborhoods in Mumbai.
- Latitude and longitude coordinates of those neighborhoods.
- Venue data, particularly data related to shopping malls.


## Sources of data and methods to extract them
This [Wikipedia page](https://en.wikipedia.org/wiki/Category:Neighborhoods_in_Mumbai) contains a list of neighborhoods in Mumbai. We will use web scraping techniques to extract the data, with the help of Python requests and beautifulsoup packages. Then we will get the geographical coordinates of the neighborhoods using Python Geocoder package which will give us the latitude and longitude coordinates of the neighborhoods.
After that, we will use Foursquare API to get the venue data for those neighborhoods.


## Methodology
First, we will do web scraping using Python requests and beautifulsoup packages to extract the list of neighborhoods data from Wikipedia. Then, we will use the Geocoder package that will allow us to convert address into geographical coordinates in the form of latitude and longitude. After gathering the data, we will populate the data into a pandas DataFrame and then visualize the neighborhoods in a map using Folium package. This allows us to perform a sanity check to make sure that the geographical coordinates data returned by Geocoder are correctly plotted in the city of Mumbai.

Next, we will use Foursquare API to get the top 30 venues that are within a radius of 2000 meters. We then make API calls to Foursquare passing in the geographical coordinates of the neighborhoods in a Python loop. Foursquare will return the venue data in JSON format and we will extract the venue name, venue category, venue latitude and longitude. With the data, we can check how many venues were returned for each neighborhood and examine how many unique categories can be curated from all the returned venues. Then, we will analyze each neighborhood by grouping the rows by neighborhood and taking the mean of the frequency of occurrence of each venue category. By doing so, we are also preparing the data for use in clustering. Since we are analyzing the “Shopping Mall” data, we will filter the “Shopping Mall” as venue category for the neighborhoods.

Lastly, we will perform clustering on the data by using k-means clustering. We will cluster the neighborhoods into 3 clusters based on their frequency of occurrence for “Shopping Mall”. The results will allow us to identify which neighborhoods have higher concentration of shopping malls while which neighborhoods have fewer number of shopping malls. Based on the occurrence of shopping malls in different neighborhoods, it will help us to answer the question as to which neighborhoods are most suitable to open new shopping malls.


## Result

- Red Cluster: Least number of Shopping Malls.
- Purple Cluster: Moderate number of Shopping Malls.
- Green Cluster: Most number of Shopping Malls.
