# nosql-challenge
The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. The editors of a food magazine, Eat Safe, Love, need help in evaluating some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

# Requirements

# Part 1: Database and Jupyter Notebook Set Up
Use `NoSQL_setup_starter.ipynb` for this section of the challenge.

1. Import the data provided in the `establishments.json` file from Terminal. Name the database `uk_food` and the collection `establishments`. Copy the text used to import data from Terminal to a markdown cell in notebook.
2. Within the notebook, import the libraries needed: PyMongo and Pretty Print (`pprint`).
3. Create an instance of the Mongo Client.
4. Confirm that the database is created and the data is loaded properly:
  a. List the databases in MongoDB. Confirm that `uk_food` is listed.
  b. List the collection(s) in the database to ensure that `establishments` is there.
  c. Find and display one document in the establishments collection using `find_one` and display with `pprint`.
5. Assign the `establishments` collection to a variable to prepare the collection for use.

# Part 2: Update the Database
Use NoSQL_setup_starter.ipynb for this section of the challenge.

The magazine editors have some requested modifications for the database before any queries or analysis are performed for them. Make the following changes to the `establishments` collection:
1. An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked to include it in the analysis. Add the following information to the database:
![1](https://github.com/Pooja14n/nosql-challenge/assets/144713762/8323cb9d-cad4-4a6f-b71a-4a741a807d44)
2. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the `BusinessTypeID` and `BusinessType` fields.
3. Update the new restaurant with the `BusinessTypeID` found.
4. The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.
5. Some of the number values are stored as strings, when they should be stored as numbers.
  a. Use `update_many` to convert `latitude` and `longitude` to decimal numbers.
  b. Use `update_many` to convert `RatingValue` to integer numbers.

# Part 3: Exploratory Analysis
Eat Safe, Love has specific questions they want answer to, which will help them find the locations they wish to visit and avoid.

Use NoSQL_analysis_starter.ipynb for this section of the challenge.

Some notes to be aware of while exploring the dataset:
  a. `RatingValue  refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.
Note: This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. We will coerce non-numeric values to nulls during the database setup before converting ratings to integers.
  b. The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.
Use the following questions to explore the database, and find the answers, so it can be provideed to the magazine editors.
Unless otherwise stated, for each question:
  a. Use `count_documents` to display the number of documents contained in the result.
  b. Display the first document in the results using `pprint`.
  c. Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.
    1. Which establishments have a hygiene score equal to 20?
    2. Which establishments in London have a `RatingValue greater` than or equal to 4?
    3. What are the top 5 establishments with a `RatingValue` of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
    4. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local            authority areas.
      The first 5 rows of your resulting DataFrame should look something like this:
    ![2](https://github.com/Pooja14n/nosql-challenge/assets/144713762/da50957b-b3ee-436c-9aa3-e88a1f1fdfb3)

# References
Referred to various class activity exercises, got support from Assistant Instructor, and websites for: Documentation for Python, Pandas, and MongoDB.

# Files submitted including this README File
1. Resources Folder -> establishments.json (contains the data provided for the analysis)
2. NoSQL_setup_starter.ipynb (contains the code for Database and Jupyter Notebook Set Up & to Update the Database)
3. NoSQL_analysis_starter.ipynb (contains the code for Exploratory Analysis).
      
