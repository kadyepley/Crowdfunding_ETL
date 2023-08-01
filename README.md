# Crowdfunding_ETL

For this project, an ETL pipeline was built using Python, Pandas, and Python dictionary methods in order to extract and transform the data. CSV files were created from the transformed data, providing details for creating an ERD and a table schema. This CSV file data was imported into a Postgres database.

To complete this project, the following steps were taken: 
   1. Create the Category and Subcategory DataFrames
   2. Create the Campaign DataFrame
   3. Create the Contacts DataFrame
   4. Create the Crowdfunding Database

##Create the Category and Subcategory DataFrames
Using the providied Excel file, "crowdfunding.xlsx", a DataFrame was created with the two column names, "category_id" and "category". 
This new DataFrame was then exported to a new csv called, "category.csv". These steps were repeated for the "subcategory_id" and "subcategory" columns, creating a "subcategory.csv" file. 

##Create the Campaign DataFrame
Using the same providied Excel file, "crowdfunding.xlsx", a new DataFrame was created with the following columns (including conversions): 
      -cf_id
      -contact_id
      -company_name
      -"blurb", renamed to "description"
      -"goal", converted to float
      -"pledged", converted to float
      -outcome
      -backers_count
      -country
      -currency
      -"launched_at" column, renamed to "launch_date" and the UTC times converted to the datetime format
      -"deadline" column, renamed to "end_date" and the UTC times converted to the datetime format
      -"category_id", with unique identification numbers matching those in the "category_id" column of the category DataFrame
      -"subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame

This new DataFrame was then converted to a new csv called, "campaign.csv". 

##Create the Contacts DataFrame
Using Pythons Dictionary methods, data was extracted and transformed from the "contacts.xlsx" Excel file into a new DataFrame. Each row was converted into a dictionary by iteration. The dictionary values from the keys were extracted by using Python list comprehensions. These values were then added to to a new list. A new DataFrame was created contaiing the extracted data and the "name" column was split to show "first_name" and "last_name" columns. Finally, the DataFrame was exported as "contacts.csv". 

##Create the Crowdfunding Database
Once all the csv files were made, an Entity Relationship Diagram (ERD) was created to connect the Primary Keys and Foreign Keys along with other constraints. This database schema was saved as a Postgres file called "crowdfunding_db_schema.sql". The correlating tables were created in a Postgres database called "crowdfunding_db". The corresponding CSV files were then imported to the SQL tables. 
