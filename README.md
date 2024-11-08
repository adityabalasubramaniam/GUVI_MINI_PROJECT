Project Title:
Census Data Standardization and Analysis Pipeline

Technologies used:
Python,
SQL,
MongoDB,
Streamlit

Project Workflow and Execution for Census Data Pipeline
Phase 1: Initial Setup and Data Extraction
Set Up the Environment

Install Required Libraries: Make sure libraries like pandas, sqlalchemy, pymongo, streamlit, os and numpy are installed.
Configure Database Connections:
Set up MongoDB and SQL database connections using MongoDB URI and SQLAlchemy connection strings.
Extract Data

Load Dataset: Download or connect to the dataset URL, read it into a Pandas DataFrame.
Load Additional Files:
Telangana district list (Telangana.txt), if not provided within the main dataset.
Any other auxiliary files needed for tasks (e.g., mappings or external data).
Phase 2: Data Cleaning and Transformation
Task 1: Rename Column Names

Execution:
Create a dictionary of old column names and their respective new names (e.g., {"State name": "State/UT", ...}).
Use Pandas rename function to rename columns in the DataFrame.
Validation:
Print column names to confirm that renaming has been applied correctly.
Task 2: Standardize State/UT Names

Execution:
Apply a function to capitalize only the first letter of each word in State/UT names, with exceptions for words like “and”.
Validation:
Check unique values in the State/UT column to confirm proper formatting.
Task 3: New State/UT Formation

Execution:
Load Telangana districts from Telangana.txt and update State/UT from “Andhra Pradesh” to “Telangana” for matching districts.
Change districts “Leh” and “Kargil” from “Jammu and Kashmir” to “Ladakh”.
Validation:
Verify by listing affected districts and confirming the correct State/UT names.
Phase 3: Handle Missing Data
Task 4: Calculate and Fill Missing Data
Execution:
Calculate missing data percentages for each column and store these metrics.
Fill missing data based on given relationships (e.g., Population = Male + Female).
Log and compare the amount of missing data before and after filling.
Validation:
Print summary of missing data before and after filling to confirm improvements in data completeness.
Phase 4: Data Storage in MongoDB
Task 5: Save Processed Data to MongoDB
Execution:
Convert the DataFrame to a dictionary and insert it into MongoDB with a collection named census.
Validation:
Confirm data insertion by querying MongoDB and ensuring the data structure is correct.
Phase 5: Data Migration to SQL Database
Task 6: Load Data from MongoDB to SQL Database
Execution:
Retrieve data from MongoDB and load it into a SQL database table, with each table name corresponding to the filename without the extension.
Define primary and foreign keys based on data schema requirements.
Validation:
Verify SQL tables by running simple queries to ensure data integrity and relationships are set up correctly.
Phase 6: Data Analysis and Visualization with Streamlit
Task 7: Query and Display Data in Streamlit
Execution:
Write SQL Queries: Define queries for each analysis task (e.g., total population per district, literate males/females, household characteristics).
Implement Streamlit Dashboard:
Create a Streamlit application with each query represented in different sections or tabs.
Use tables, charts, or other visual elements to display query results interactively.
Validation:
Test each query on Streamlit to ensure data is displayed correctly and visualizations are clear and informative.

finally the output is displayed in the seperate localhost with the help of streamlit as below attached image.
/////

Clone the Project Repository:
open cmd
-this will open the command prompt shell.

git clone ////
-This will create a local copy of the repository in a folder named after the repository. 

Navigate into this project folder:
cd guvi_DE_MP1

.code - to open the vs code editor.

run the code after installing the necessary dependencies(pip install  pandas, sqlalchemy, pymongo, streamlit,os and numpy).
Make sure that you have installed the mysql workbench and Mangodb to store and retrieve data while running the pipeline.


