# nosql-challenge

## Part 1: Database and Jupyter Notebook Set Up
Before beginning work in full, I had to import the provided json file into a MongoDB database and collection from the terminal. I then verified that they were successfully and correctly imported by listing the databases to ensure the "uk_food" one was included. As a final step, I confirmed that the "establishments" collection was also there, and displayed one document from the collection.
## Part 2: Update the Database
Now that it was imported, it was time to make a few updates. The first step was adding a new restaurant "Penang Flavours", which was unfortunately missing the "BusinessTypeID". To find that, I had to run a short query looking for a BusinessType of "Restaurant/Cafe/Canteen" to bring back the BusinessTypeID. Once located, this was also added to the document for Penang Flavours. Per the request, I also dropped all establishments from Dover, in order to keep the database clean and free of any unnecessary or unwanted data. The final step before performing some exploratory analysis was to ensure that the latitude and longitude values were decimals, and that RatingValue was set to an integer (both were previously strings).
## Part 3: Exploratory Analysis
Before beginning to explore and analyze the data, I first altered the NoSQL_analysis_starter imports to include "import pandas as pd" to assist with creating dataframes. Additionally, for questions 1, 2 and 4, I split the cells apart to separate cells for converting into a Pandas Dataframe, print the number of documents found in the result, and printing the first 10 results. This provides the benefit of those results all displaying independently and at the same time.  
The questions I sought to answer were:  
1. Which establishments have a hygiene score equal to 20?
2. Which establishments in London have a RatingValue greater than or equal to 4?  
  * This particular query required the use of $regex to find establishments in London, as the proper LocalAuthorityName seems to be "City of London"
4. What are the top 5 establishments with a RatingValue rating value of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
  * This included the addition of a "sort" argument, to make sure they were descending by lowest hygiene score.
5. How many establishments in each Local Authority area have a hygiene score of 0?
  * The final query included an opportunity to include an aggregate function in order to manage the grouping along with the query.
