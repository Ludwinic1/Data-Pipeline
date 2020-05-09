# Data Engineer Data Pipeline

This project builds a data pipeline utlizing the ETL process. The python script does the following automatically:

1. Extracts data from an excel worbkook with two sheets containing one with jumbled data (data sheet) and another with officer name/code data (officer codes sheet).

2. Creates a dictionary based on the officer name and their code found in the officer codes sheet. This is to ensure data integrity and that the correct officer name is linked to their correct officer code throughout the script. 

3. Transforms and cleans the data sheet by checking if the primary officer name exists (from the created dictionary) and then if their officer name/code is correct, it updates the secondary officer name and secondary officer code to match. If an officer code isn't correct or the names aren't consistent, it updates them. If there is an uknown primary officer name, a new sheet (incorrect row data) is created with those rows to examine further. It also prints helpful info on the incorrect data. 

4. Creates a new worksheet named 'Cleaned Data' and loads the updated data into it.

5. Creates a new worksheet named 'Incorrect Row Data' and loads the incorrect rows (uknown primary officer names) into it.

6. Loads the cleaned data into a SQL server database table by first connecting to SQL Server using the pyodbc module and then loading the data into the table. 

New data or additional officers could be added later and the script will include the additional info and ensure data integrity. 
The script is also flexible enough that if a new officer is listed in or if a new person takes over a current officer code, it is easy to adjust to ensure the data integrity is kept and data is updated correctly. 

## Instructions
Click on the Data Pipeline.ipynb above to see the code.  You can also click on Fictional Data.xlsx to see the original Excel file and Actual End Fictional Data.xlsx to see the updated one.

## Tech Stack Used:
-Python: openpyxl, pandas, and pyodbc modules

-SQL

-SQL Server database

## Original Workbook Image

![](Test%20Image%201.PNG)

# After Script Workbook Image

<img src = "After Workbook Image.PNG" height=400>

