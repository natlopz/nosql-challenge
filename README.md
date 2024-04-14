# nosql-challenge
Module 12 Challenge

## Part 1: Database and Jupyter Notebook Set Up
Import the data provided in the `establishments.json` file from your Terminal. Name the database `uk_food` and the collection `establishments`.

Within this markdown cell, copy the line of text you used to import the data from your Terminal. This way, future analysts will be able to repeat your process.

e.g.: Import the dataset with 'mongoimport --db uk_food --collection establishments --drop --jsonArray --file establishments.json'

Import dependencies. Create an instance of MongoClient. Confirm that our new database was created. Assign the uk_food database to a variable name. Review the collections in our new database. Access the establishments collection. Review a document in the establishments collection. Assign the collection to a variable.

## Part 2: Update the Database
1. An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked you to include it in your analysis. Add the following restaurant "Penang Flavours" to the database.

Create a dictionary for the new restaurant data. Insert the new restaurant into the collection. Check that the new restaurant was inserted.

2. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the `BusinessTypeID` and `BusinessType` fields

Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields. Return BusinessTypeID and BusinessType only. Retrieve and print results.

3. Update the new restaurant with the `BusinessTypeID` you found.

Update the new restaurant with the correct BusinessTypeID. Define the query for finding the restaurant "Penang Flavours". Confirm that the new restaurant was updated. 

4. The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.
5. 
Find how many documents have LocalAuthorityName as "Dover". Delete all documents where LocalAuthorityName is "Dover". Check if any remaining documents include Dover. Check that other documents remain with 'find_one'.

5. Some of the number values are stored as strings, when they should be stored as numbers.

Use `update_many` to convert `latitude` and `longitude` to decimal numbers. Change the data type from String to Decimal for longitude and latitude. Update the document with new float values. Use update_many to convert RatingValue to integer numbers. Set non 1-5 Rating Values to Null. Change the data type from String to Integer for RatingValue. Check that the coordinates and rating value are now numbers. 

## Part 3: Exploratory Analysis
Unless otherwise stated, for each question: 
* Use `count_documents` to display the number of documents contained in the result.
* Display the first document in the results using `pprint`.
* Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.

1. Which establishments have a hygiene score equal to 20?
   Number of establishments with a hygiene score of 20: 41

Find the establishments with a hygiene score of 20. Use count_documents to display the number of documents in the result. Display the first document in the results using pprint. Convert the result to a Pandas DataFrame. Display the number of rows in the DataFrame. Display the first 10 rows of the DataFrame. 

2. Which establishments in London have a RatingValue greater than or equal to 4?
   Number of establishments in London with a rating of 4 or higher: 33

Find the establishments with London as the Local Authority and has a RatingValue greater than or equal to 4. Use count_documents to display the number of documents in the result. Display the first document in the results using pprint. Convert the result to a Pandas DataFrame. Display the number of rows in the DataFrame. Display the first 10 rows of the DataFrame. 

3. What are the top 5 establishments with a `RatingValue` rating value of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

Search within 0.01 degree on either side of the latitude and longitude., rating value must equal and sort by hygiene score. Using latitude and longtitude date from NoSQL_setup_starter.ipynb. Define geographic search parameters. Print the results. Convert result to Pandas DataFrame. 

4. How many establishments in each Local Authority area have a hygiene score of 0?
   Number of Local Authorities with establishments having a hygiene score of 0: 55

Create a pipeline that: Matches establishments with a hygiene score of 0, Groups the matches by Local Authority, and Sorts the matches from highest to lowest. Print the number of documents in the result. Print the first 10 results. Convert the result to a Pandas DataFrame. Display the number of rows in the DataFrame. Display the first 10 rows of the DataFrame. 

