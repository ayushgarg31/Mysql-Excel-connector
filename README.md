# Mysql-Excel-connector
Only xlsx files are excepted for now.
Library requirements - 
* openpyxl
* mysql.connector
* tkinter

## What all can be done - 
* Delete an existing database.
* Create a new database.
* Export the database to a excel file.
* Edit the database using excel sheet.
  * Deleting existing tables.
  * Creating new tables with primary key and foreign key constraints (other constraints are not handled). Foreign key has on delete cascade.
  * Add new column or delete a column. (Primary key columns must not be added or deleted, to do so delete the table and then again create it.)
  * Foreign key constraints can be added or removed.
  * Remove rows from database.
  * Add rows into database.
  * Modify rows in database.
  * *Do Not change the datatype of an attribute after defining for first time (to do this drop attribute and then again add it with changed data type).

## Specification of the xlsx file for manipulating database using it -
* Each sheet represents a new table in the database (name of sheet is the name of table).
* First row is for the attribute names.
* Second row specifies datatype of the attribute (int(11), varchar(120) etc., please write these exact as mysql stores them).
* Thrid line is for specifying primary keys. All those attributes who are in primary key write 'PRI' under them.
* Fourth line is for specifying foreign key constraints. Under the attribute write 'REFERENCES @tablename(@attributename)'.
* From fifth line you can start entering data.
* Please do not leave any blank row or column in the middle.

authcode |	pubcode
---------|---------
int(11) |	int(11)
PRI |
REFERENCES author(authcode) |	REFERENCES publisher(pubcode)
1 |	1
2 |	2
4 |	2
9 |	2
7 |	3


## How to use -
* Run main.ipynb
* A new window will appear. Enter the username and password of your mysql and click login.
* Then choose if you want to modify an existing database or create a new one or delete an existing database.

#### Deleting an existing database - 
* Enter name of database.
* Enter 'y' to confirm you want to delete.

#### Modifying an existing database - 
* Enter the name of the database you want to modify.
* There are 2 options - To export the database to a spreadsheet type 1, to manipulate data using spreadsheet type 2
* Enter the name of file along with it's extension (eg. test.xlsx).

#### Creating a new database - 
* Enter the name of database.
