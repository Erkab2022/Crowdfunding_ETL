# **Project 2 for the University of Minnesota Data Visualization and Analytics Bootcamp**

## **Contributors: Eriel Kabambi, Oliviera Wanderson (Group 15)**

### Description
This project involves constructing an Extract, Transform, Load (ETL) pipeline utilizing Python and Pandas. 
The data extraction and transformation will be accomplished through either Python dictionary methods or regular expressions.

### Goal
The objective is to generate four CSV files, which will serve as the basis for creating an Entity-Relationship Diagram (ERD) and a corresponding table schema. 
Subsequently, the data contained within the CSV files will be imported into a PostgreSQL database.

### Instructions
Based on the files provided in the Resources folder, we will proceed with the following steps:
1.	Create the Category and Subcategory DataFrames: Extract and organize data from the provided files to create DataFrames representing categories and subcategories.
2.	Create the Campaign DataFrame: Extract and organize data from the provided files to create a DataFrame representing campaigns.
3.	Create the Contacts DataFrame: Extract and organize data from the provided files to create a DataFrame representing contacts.
4.	Create the Crowdfunding Database: Using the DataFrames created in the previous steps, establish a PostgreSQL database schema and upload the data into corresponding tables.

### Result
*1. Create the Category and Subcategory DataFrames:*
After imported our dependencies and read the crowfunding.xlx file, we get the summary of each column and the datatype to ensure to proceed to the category and subcategory.
The crowfunding is a table with 14 columns where the last column takes category and subcategory.
The goal was to split that column into two separate columns and create two different DataFrame. Each Dataframe will contain the id and the description has following:
category_df: category_id, category
subcategory_df: subcategory_id, subcategory

*2.Create the Campaign DataFrame:*
Utilizing the crowdfunding data, we constructed the campaign DataFrame by renaming certain columns and converting others as needed.
Subsequently, we merged the campaign_df with the category_df based on the "category" column and the subcategory_df based on the "subcategory" column.
We also performed a cleanup operation by dropping unnecessary columns.

*3.Create the Contacts DataFrame:* 
Based on the contact_info file provided, we used Pandas to read it into a DataFrame. Each row contained a dictionary with contact_id, name, and email. 
Our goal was to create a DataFrame with columns for contact_id, first_name, last_name, and email. We converted the DataFrame into a JSON file, then split the name column into first_name and last_name, and finally cleaned up the data before finalizing our table.

*4.Create the Crowdfunding Database:* 
After creating the four CSV files, we analyzed them and drafted an ERD using QuickDBD. Using this ERD, we designed table schemas for each CSV file, detailing data types, primary keys, foreign keys, and other constraints. The schema was saved as crowdfunding_db_schema.sql on GitHub. We then set up crowdfunding_db in PostgreSQL and proceeded to create tables in the appropriate order to manage foreign keys. Verification of table creation was done via SELECT statements. Following this, CSV data was imported into corresponding SQL tables, and data accuracy was confirmed using SELECT queries.
