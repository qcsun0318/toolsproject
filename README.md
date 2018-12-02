This is a tool to scrape restuartant information! 
===================================
We are Group 37 in Section 2. 

Description: 
-------------
This project’s main purpose is to get useful data from internet based on users’ inputs, and return results in data frame as well as map presentation. The first part accesses data through API and the second part did a more detailed web scraping by requesting HTML pages. 

The first method we implemented is to use the Yelp API key provided by Yelp at the creation of an account. The function "webscrapingYelp()" is creating a dataframe based on the research keyword that we input. The advantage of this method is that we are not limited in the number of requests.

The second part is what all of us mainly work on. The first function, "get_info," uses the url link of a specific restaurant as input, and then scrapes information wanted by finding tags and attributes of the restaurant’s page in XML format. 

Our second function, "get_businesses," uses the keyword and location that a user enters to get an url of all the business listings. Then, we write a loop that uses get_info function to search for detailed information of each restaurant, which are put into a data frame. Users can choose the amount of results they want and the function can automatically scrap the next pages until the number requirement reached. Three sortby functions are added so that people can sort the listings based on their interests. 

After a table of listings is presented to our user, we nicely ask if the results are satisfactory. If the answer is “no,” the function "further_rec" will recommend 10 more restaurants in the same location but in another relevant cuisine category. It functions similarly to the "get_businesses" function. Three variables in the "get_businesses" function are made global to accommodate the "further_rec" function. This function identifies the two most common cuisine styles from the user’s initial search, compare them to the initial keyword, and set the different one as the new keyword. 

We also try a little data visualization. Based on the longitude and latitude scraped from the restuarant page, we create a json object and applied it on map with the folium package to show marks of the restaurants returned, so it gives users a better idea of the restaurants locations.



Installation: 
-------------

    $ git clone git@github.com:qcsun0318/toolsproject.git
    $ cd toolsproject
    $ pip install -r requirements.txt


Run instructions:
-------------
Our codes are all in the scrape_restaurant.ipynb file in this repository. 

After you run “res” and questions jump out, you can enter any food and cuisine keyword but no keyword for other kinds of businesses such as manicure and theater, and you can only enter an address in the U.S.. 

Since originally we were interested in exploring restaurants in New York City, we set up the folium map in Manhattan. If you enter a location far away, you would need to zoom out for the marks to show on the map. We apologize for the inconvenience.

If you run “res” to call the "get_businesses" function multiple times in a short period of time, you are likely to be blocked temporarily by Yelp and get a “NoneType” error. 
