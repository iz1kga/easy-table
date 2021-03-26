# easy-table
### i was using this lib and it disappeared from PyPI and Git:
### originally developed by TheGuyFromCanada
### if you are the author please contact me!!!!



# Easy Table

Easy Table is a python module that provides an easy way to work with tables. It provides functionality for creating, modifying and cleaning displaying them in a console.
Features

    Automatically formatted table
    Insert, delete and update data
    Checkpoint data
    Sort data

## Install

pip install easy-table
Usage

from easy_table import EasyTable

#Create the table and define the structure
table = EasyTable("My Table")
table.setCorners("/", "\\", "\\", "/")
table.setOuterStructure("|", "-")
table.setInnerStructure("|", "-", "+")

print("This is the table structure:")
table.displayTableStructure()
print()

#Set the data in the table
table.setData([
    {"id": 1, "name": "Tim", "age": 33},
    {"id": 2, "name": "Bob", "age": 28},
    {"id": 3, "name": "John", "age": 41}
  ])

#Display the table
print("This is the table:")
table.displayTable()

Shows

This is the table structure:
----TABLE PROPERTIES----
Table Corners: / \ \ /
Table Outer: | -
Table Inner: | - +

This is the table:
/-----------\
|id|name|age|
|--+----+---|
|1 |Tim |33 |
|--+----+---|
|2 |Bob |28 |
|--+----+---|
|3 |John|41 |
\-----------/

API
class easy_table.EasyTable(table_name="")

Creates EasyTable object

Returns EasyTable object
Parameter 	Type 	Default 	Description
table_name 	str 	"" 	Name of table
classmethod EasyTable.setTableName(table_name)

Sets the name of the table
Parameter 	Type 	Default 	Description
table_name 	str 	"" 	Name of table
classmethod EasyTable.setCorners(top_left, top_right, bottom_left, bottom_right)

Sets the strings used as the corners of the table
Parameter 	Type 	Default 	Description
top_left 	str 	N/A 	Top Left Corner
top_right 	str 	N/A 	Top Right Corner
bottom_left 	str 	N/A 	Bottom Left Corner
bottom_right 	str 	N/A 	Bottom Right Corner
classmethod EasyTable.setOuterStructure(vertical_outer, horizontal_outer)

Set the strings used as the outer structure (border) of the table
Parameter 	Type 	Default 	Description
vertical_outer 	str 	N/A 	The border on the left and right of the table
horizontal_outer 	str 	N/A 	The border at the top and bottom of the table
classmethod EasyTable.setInnerStructure(vertical_inner, horizontal_inner, intersection_inner)

Set the strings used as the inner structure (separating cells) of the table
Parameter 	Type 	Default 	Description
vertical_inner 	str 	N/A 	Separates columns
horizontal_inner 	str 	N/A 	Separates rows
intersection_inner 	str 	N/A 	Corners of a cell
classmethod EasyTable.displayTableStructure()

Displays the strings that make up the table structure

Example:

----TABLE PROPERTIES----
Table Corners: / \ \ /
Table Outer: | -
Table Inner: | - +

classmethod EasyTable.setData(data)

Set the data in the table
Parameter 	Type 	Default 	Description
data 	list 	N/A 	Data for the table, either list of dicts or list of lists
classmethod EasyTable.setColumns(columns)

Manually set the columns the table has
Parameter 	Type 	Default 	Description
columns 	list 	N/A 	Column names for the table
classmethod EasyTable.addColumns(columns)

Add columns to the table
Parameter 	Type 	Default 	Description
columns 	dict 	N/A 	Column names and default values to be added to the table
classmethod EasyTable.removeColumns(columns)

Remove columns from the table
Parameter 	Type 	Default 	Description
columns 	list 	N/A 	Column names to be removed from the table
classmethod EasyTable.displayTable()

Displays table with data and column names, with the table being formatted so the data in the cells are all centered

Example:

/-----------\
|id|name|age|
|--+----+---|
|1 |Tim |33 |
|--+----+---|
|2 |Bob |28 |
|--+----+---|
|3 |John|41 |
\-----------/

classmethod EasyTable.sortData(condition=None, reverse=False)

Sort the table data based off condition
Parameter 	Type 	Default 	Description
condition 	function 	None 	Function providing what to sort by
reverse 	bool 	False 	If the sorted data should be reversed
classmethod EasyTable.commitData()

Set the current table data as the new backup point
classmethod EasyTable.rollbackData()

Set the data in the table equal to the data from the backup point
classmethod EasyTable.insertData(new_data)

Add new rows of data to the table
Parameter 	Type 	Default 	Description
new_data 	list or dict 	N/A 	New rows to be added to the table
classmethod EasyTable.deleteData(condition=None)

Delete rows of data from the table based off condition
Parameter 	Type 	Default 	Description
condition 	function 	None 	Function providing whether or not the row should be deleted
classmethod EasyTable.updateData(value, condition=None)

Update rows of data withe value based off condition
Parameter 	Type 	Default 	Description
value 	function 	N/A 	Function providing the value the row should be updated to
condition 	function 	None 	Function providing whether or not the row should be updated
License

Easy-Table is licensed under the MIT License
