# toolsproject

We are Group 37 in Section 2. We proposed to scrape data from Yelp. 

Description: 
The first function, get_info, uses the url link of a specific restaurant as input, and then scrapes information of the restaurant, such as its price range and phone number. It also scrapes a few attributes that we are interested in in the “more business info” section from the website. 

Our second function, get_businesses, uses the keyword and location that a user enters to get an url of all the business listings. Then, we write a loop that uses get_info function to search for detailed information of each restaurant, which are put into a data frame. Three filters are added so that people can sort the listings. 

We also try a little data visualization. We create a map with the folium package to show marks of the restaurants in the data frame.

After a table of listings is presented to our user, we nicely ask if the results are satisfactory. If the answer if no, the function further_rec will recommend 10 more restaurants in the same cuisine category in the same location.

However, the scraping method we are using is limited in the number of requests. That is why we tried to implement an alternative method and exploit the yelp api key provided by Yelp at the creation of an account. The function webscrapingYelp() is creating a dataframe based on the research keywords that we input


Installation: 
Below are packages we use.
requests
Beautifulsoup
json
pandas
numpy
re 
collections
folium

Run instructions:
If you run “res” to call the get_businesses function multiple times in a short period of time, you are likely to be blocked temporarily by Yelp and get a “NoneType” error. 

Since originally we were interested in exploring restaurants in New York City, we set up the folium map in Manhattan. If you enter a location far away, you will need to zoom out for the marks to show on the map. We apologize for the inconvenience.
