# New York Airbnb Data Analysis Project

# Initial Question?
I am an individual looking to buy a property in New York to List on Airbnb. I want to know which neighborhood would be the most popular and profitable to invest in. What should I look at? 
First Step : Downloading the Data
In order to answer the initial question, we downloaded the New York Airbnb Data from the link below:
https://www.kaggle.com/dgomonov/new-york-city-airbnb-open-data

# Investigating and Cleaning the Data:
After downloading the data, we converted it to a dataframe and investigated. We decided to distribute each one of the 5 neighbourhood groups (Manhattan, Brooklyn, Bronx, Staten Island, Queens) to a member of the project group. 
As a part of the clean up, first we got rid of the columns we do not need. Then we filled the missing values properly. 
In the end of this step, we had 5 different dataframes to work on and each member of the project was responsible from one. 
Using New York City Crime Data API
We thought getting the number of crimes data for each listing can be a valuable parameter while making our final decision. This data is available on the internet and after some successful API calls we were able to retrieve the data. 
For this project, we applied this data only on 100 listings taken randomly from each neighbourhood group. We assumed this is a representation of the overall data.

# Phase 1: Determine the Outliers
As phase 1 of the project, we defined the outliers and cleaned up the data to only include what is lower than upper bound for minimum nights of stay and price.
Additionally, we removed the data that has only ‘0’ reviews.
The reason we cleaned up the data from outliers is because some of them have significantly high prices. We concluded that the initial investment for the property would be too high to get to that high rental prices. Therefore we cleaned the data to only include the price ranges we are interested in. 
We removed the listings with “0’ reviews because they are not reliable.

# Phase 2: Shaping the DataFrame
We asked ourselves the question: What is the best way of looking at this data with many variables?
After brainstorming, we agreed on the best way. We cut the prices in bins to create price ranges. And then we grouped the data by neighbourhood, room type and price range.
For the columns, we filtered number of reviews, minimum nights of stay and minimum price to stay (a data we created by combining price and minimum nights of stay), and aggravated them using mean, sum, min and max functions. 
Then we sorted the top 25 of these data by listing count, highest to lowest. 

# Phase 3: Defining the Parameters
After finalizing the dataframe, the question was: what parameters do we need to define to answer our initial question and pick the best neighbourhood?
We found 3;
Popularity
Worth
Profitability
Next step was to determine each of these parameters for neighbourhoods, and in the end pick the best one. 
# Phase 4: Which Neighbourhood is the Most Popular?
In order to determine popularity for each neighbourhood, we calculated the total number of listings for each neighbourhood in the top 25. 
We supported our data by creating a bar graph.

# Phase 5: Which Neighbourhood has the Most Value?
In order to determine worth for each neighbourhood, we calculated the sum of mean min price to stay for each neighbourhood in the top 25.
We supported our data by creating a bar graph.

# Phase 6: Which Neighbourhood is the Most Profitable?
Calculating the profitability was a bit more complicated. Firstly, we selected the top 5 neighbourhoods by comparing the two graphs we have generated before. 
Afterwards, since we do not have the data for how many days a listing is booked out for in a given year, we had to come up with our own calculation. 
For the selected 5 neighbourhoods, we calculated their percentage of number of listings amongst themselves. And then, we used this percentage to replace the missing data for number of bookings per year. We named the data “Popularity by Selected Neighbourhoods”
In order to calculate profitability, we multiplied the popularity by selected neighbourhood and worth. We generated a horizontal bar graph to support our data. 

# Making the Final Decision
We performed the phases mentioned above for each neighbourhood group separately, and in the end, considering the popularity, worth, profitability and crime data, we decided Williamsburg, Brooklyn has the best prospects for an Airbnb property investment in New York City.



### References: 
*https://www.kaggle.com/  - NY airbnb open dataset
*https://data.cityofnewyork.us – Crime API
*matplotlib.org
