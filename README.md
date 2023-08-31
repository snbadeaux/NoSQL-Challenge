# NoSQL-Challenge


Instructions


The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.<br>


Part 1: Database and Jupyter Notebook Set Up


Use NoSQL_setup_starter.ipynb for this section of the challenge.<br>
1.	Import the data provided in the establishments.json file from your Terminal. Name the database uk_food and the collection establishments. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.<br>
2.	Within your notebook, import the libraries you need: PyMongo and cPretty Print (pprint).<br>
3.	Create an instance of the Mongo Client.<br>
4.	Confirm that you created the database and loaded the data properly:<br>
o	List the databases you have in MongoDB. Confirm that uk_food is listed.<br>
o	List the collection(s) in the database to ensure that establishments is there.<br>
o	Find and display one document in the establishments collection using find_one and display with pprint.<br>
5.	Assign the establishments collection to a variable to prepare the collection for use.<br>

   
Part 2: Update the Database


Use NoSQL_setup_starter.ipynb for this section of the challenge.<br>
The magazine editors have some requested modifications for the database before you can perform any queries or analysis for them. Make the following changes to the establishments collection:<br>
1.	An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked you to include it in your analysis.<br>
2.	Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.<br>
3.	Update the new restaurant with the BusinessTypeID you found.<br>
4.	The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.<br>
5.	Some of the number values are stored as strings, when they should be stored as numbers.<br>
1.	Use update_many to convert latitude and longitude to decimal numbers.<br>
2.	Use update_many to convert RatingValue to integer numbers.<br>

   
Part 3: Exploratory Analysis


Eat Safe, Love has specific questions they want you to answer, which will help them find the locations they wish to visit and avoid.<br>
Use NoSQL_analysis_starter.ipynb for this section of the challenge.<br>
Some notes to be aware of while you are exploring the dataset:<br>
•	RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.<br>
o	Note: This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. We will coerce non-numeric values to nulls during the database setup before converting ratings to integers.<br>
•	The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.<br>
Use the following questions to explore the database, and find the answers, so you can provide them to the magazine editors.
Unless otherwise stated, for each question:<br>
•	Use count_documents to display the number of documents contained in the result.<br>
•	Display the first document in the results using pprint.<br>
•	Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.<br>
1.	Which establishments have a hygiene score equal to 20?<br>
2.	Which establishments in London have a RatingValue greater than or equal to 4?<br>
Hint: The London Local Authority has a longer name than "London" so you will need to use $regex as part of your search.<br>
3.	What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?<br>
Hint: You will need to compare the geocode to find the nearest locations. Search within 0.01 degree on either side of the latitude and longitude.<br>
4.	How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.<br>
Hint: You will need to use the aggregation method to answer this.<br>


Sources:

Python Tutorial. (n.d.). https://www.w3schools.com/python/<br>
Stack Overflow - Where Developers Learn, Share, & Build Careers. (n.d.). Stack Overflow. https://stackoverflow.com/<br>
https://chat.openai.com/: used to help debug problematic for loop.<br>
Starter code given from boot camp class and instructions<br>
