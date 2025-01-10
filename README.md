# nosql-challenge
By: Itzel Vázquez Sánchez

## Project Description

This Week's Challenge consists of three parts. 

### Part 1: Database and Jupyter Notebook Set Up
Use _NoSQL_setup_starter.ipynb_ for this section of the challenge.
1. Import the data provided in the establishments.json file from your Terminal. Name the database uk_food and the collection establishments. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.
2. Within your notebook, import the libraries you need: PyMongo and Pretty Print (pprint).
3. Create an instance of the Mongo Client.
4. Confirm that you created the database and loaded the data properly:
  * List the databases you have in MongoDB. Confirm that uk_food is listed.
  * List the collection(s) in the database to ensure that establishments is there.
  * Find and display one document in the establishments collection using find_one and display with pprint.
5. Assign the establishments collection to a variable to prepare the collection for use.

### Part 2: Update the Database
Use _NoSQL_setup_starter.ipynb_ for this section of the challenge.
1. Add the following information to the database:

```
{
    "BusinessName":"Penang Flavours",
    "BusinessType":"Restaurant/Cafe/Canteen",
    "BusinessTypeID":"",
    "AddressLine1":"Penang Flavours",
    "AddressLine2":"146A Plumstead Rd",
    "AddressLine3":"London",
    "AddressLine4":"",
    "PostCode":"SE18 7DY",
    "Phone":"",
    "LocalAuthorityCode":"511",
    "LocalAuthorityName":"Greenwich",
    "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",
    "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",
    "scores":{
        "Hygiene":"",
        "Structural":"",
        "ConfidenceInManagement":""
    },
    "SchemeType":"FHRS",
    "geocode":{
        "longitude":"0.08384000",
        "latitude":"51.49014200"
    },
    "RightToReply":"",
    "Distance":4623.9723280747176,
    "NewRatingPending":True
}
```

3. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.
4. Update the new restaurant with the BusinessTypeID you found.
5. The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.
6. Some of the number values are stored as strings, when they should be stored as numbers.
7. Use update_many to convert latitude and longitude to decimal numbers.
8. Use update_many to convert RatingValue to integer numbers.

### Part 3: Exploratory Analysis
Use NoSQL_analysis_starter.ipynb for this section of the challenge.

* Some notes to be aware of while you are exploring the dataset:
* _RatingValue_ refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.
* This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. We will coerce non-numeric values to nulls during the database setup before converting ratings to integers.
* The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.

Use the following questions to explore the database, and find the answers, so you can provide them to the magazine editors. Unless otherwise stated, for each question:

* Use count_documents to display the number of documents contained in the result.
* Display the first document in the results using pprint.
* Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.
* Questions: 
  1. Which establishments have a hygiene score equal to 20?
  2. Which establishments in London have a RatingValue greater than or equal to 4?
     Hint: The London Local Authority has a longer name than "London" so you will need to use $regex as part of your search.
  3. What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"
     Hint: You will need to compare the geocode to find the nearest locations. Search within 0.01 degree on either side of the latitude and longitude.
  4. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
     Hint: You will need to use the aggregation method to answer this.

The first 5 rows of your resulting DataFrame should look something like this:

![image](https://github.com/user-attachments/assets/ffd3ade3-23b6-4c58-876d-df3633350a5e)


This Project is the result of the learning lessons of Module 12: NoSQL Databases from the Data Analysis and Visualization Boot Camp 2024. The main goal is to use the acquired habilities and knowledge in a real case. 


## Table of contents

On the repository you can find the following content:

| Item  |   File Type   |         File Name              |           Description                   |
| ----- | ------------- | ------------------------------ | --------------------------------------- |
|   1   |    .ipynb     |  NoSQL_setup_starter           |First and second parts of the challenge  |
|   2   |    .ipynb     | NoSQL_analysis_starter         |    Third part of the challenge          |
|   3   |     folder    |       Resources                | contains json with data                 |


## How to Use the Project
 
 * To solve the first and second part: you can use the jupyter notebook _NoSQL_setup_starter.ipynb_. But first, you should run in your terminal the code to import the json database.
 
 * To solve the third part: you can use the jupyter notebook _NoSQL_analysis_starter.ipynb_.

## Credits 

The code of this project origins from: starter code provided by the Team of the Data Analysis and Visualization Bootcamp, the solved exercises worked in the Zoom Lessons, [Stackoverflow](https://stackoverflow.com/), [pandas documentation](https://pandas.pydata.org/docs/index.html), [PyMongo Documentation](https://pymongo.readthedocs.io/en/stable/) and Microsoft Copilot.
