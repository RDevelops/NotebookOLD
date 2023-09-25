# Definition:
A database used to keep information in tables, which are joined into datasets.
# Terminology
| Term | Defenition |
| -----| -------|
| RDMS/RDBMS | Relational Database Management System |
| Relations | Table, grid made of rows and columns. |
| Tuples | Record, row in database, Each tuple is one item (e.g. one book in a bookstore DB) |
| Attributes | Information on a record, such as the price of a book|
| Domains | The requirement for the attribute - data type, and other rules - E.G. `(int, 1, 10)`
| Cardinality | The uniqueness of an atribute, Repeated values would have a "Low cardinality" where as non-repeated values would have Cardinality
| Structured Query Language (SQL) | A programming language for sorting and storing data | 
| Entity relation | Link between two tables |
# Types of RDMS/RDBMS
| | Desktop | Server |
|--------|  --------- |---------|
| Example | Microsoft Access | Oracle, MySQL |
| Usage | Local/Development | Websites/large projects |
| Features | Guis, Wizards| Tuis, Large databases, Accessible from anywhere |

# Pros and cons
|  | Desktop | Server |
| ------ | ------ | -------|
| Pros| Cheap, Easier to use for less IT literate users, No need for internet connection | Not scaleable |
| Cons| Lesser access | Expensive |


# Example table
| ISBN | BOOK TITKE | GENRE | PRICE | PUBLISHER ID |
| -----| ------| ------| -----| -----|
| 1-XXXX-XXX-X | EXAMPLE TITLE 1 | TECHNOLOGY | £14.99 | 123 |
| 2-XXXX-XXX-X | EXAMPLE TITLE 2 | TECHNOLOGY | £19.99 | 321 |
| 3-XXXX-XXX-X | EXAMPLE TITLE 3 | FICTION | £9.99 | 213 |
| 4-XXXX-XXX-X | EXAMPLE TITLE 4 | MUSIC | £35.99 | 312 |
Each line in this [[#Terminology |Table]] is a [[#Terminology |Tuple]], each piece of information is called an [[#Terminology |Attribute]].

The "Domain" for the "Publisher ID" for example, would be to be an integer greater than 0.

ISBN - High [[#Terminology |Cardinality]], since very unique
Genre - How [[#Terminology |Cardinality]], not as unique

# Symbols

| Symbol | Name | Description | Usage |
| ----| ----| ----| ----|
| ᴗ | Union | Combine 2 tables with matching fields for all records, removing duplicates | Create a dataset of all the records from both tables |
| ᴖ | Intersect | Creates a dataset where records match in 2 tables | Creates a dataset of matched records from 2 tables |
| ⋈ | Join | Create a dataset from two or more tables | Joins 2 tables into a dataset |
| σ | Select | Select a subset of records with matching criteria | Search the table for certain information |

# Regional Algebra Sets
## SQL
In order to manipulate and retrieve data we use SQL (Structured Query Language)
SQL is based on a mathematic query language called relational algebra. Relational algebra uses a number of operations to allow us to work with our database

## Operators
| Name | Description | Usage |
|---| --- | ---|
|[[#Symbols \|Select]] | Retrieve a subset of [[#Terminology \|Tuples]] from a [[#Terminology \|Table]] that meet certain criteria | Find information you need in a [[#Terminology \|Table]] |
|[[#Symbols \|Union]] | Retrieve a subset of [[#Terminology \|Tuples]] from two [[#Terminology \|Tables]], requires both [[#Terminology \|Tables]] to have the same number of [[#Terminology \|Tuples]] and [[#Terminology \|Attributes]]| Match data between two [[#Terminology \|Tables]]
|[[#Symbols \|Intersect]] | Similar to [[#Symbols \|Union]], although only gets information from both [[#Terminology \|Tables]]. | Get the information from 2 [[#Terminology \|Tables]] with little to no requirements.
|[[#Symbols \|Join]] | Combines [[#Terminology \|Attributes ]] from two [[#Terminology \|Tables ]], [[#Terminology \|Tuples ]] from [[#Terminology \|Table ]] 1 will be shown alongside the [[#Terminology \|Tuples ]] in [[#Terminology \|Table ]] 2. Requires both [[#Terminology \|Tables ]] to have at least one [[#Terminology \|Attribute ]] in common. | Join two [[#Terminology \|Tables ]] into a dataset|
Going back to our example DB, using the `Select` operator to search for a Publisher ID of `123` Would yield this response:

| ISBN | BOOK TITKE | GENRE | PRICE | PUBLISHER ID |
| -----| ------| ------| -----| -----|
| 1-XXXX-XXX-X | EXAMPLE TITLE 1 | TECHNOLOGY | £14.99 | 123|

# Database Relations
An [[#Terminology |Entity relationship]] is the link between two [[#Terminology |tables]], it is created through having matching [[#Terminology |Attributes]] in each of the two tables. Within entity relationships we commonly model the relations between two tables as being either "generic" or "semantic"

Generic entity relationships take a higher and less specific view of the relationship. It's more concerned with what entities are related, which helps you understand the overall structure of the database.

Semantic entity relationships incorporate more of the actual attributes of the entities, and shows the primary and foreign attributes that create the relationship between the tables.

# Relational Keys
Relationship between two tables are created through matching fields that appear in both tables. These fields are known as the relational keys and there are a few different types of key.

### Example DB:
| Employee ID | Employee Username | Employee name |
| --- | --- | --- |
| 1 | 7528 | Steve |
| 2 | 9643 | Anna |
| 3 | 2389 | Ahmed |
| 4 | 4739 | Tina |

### Super Key
A super key is any attribute that can identify a tuple in a relation.
In the table above, the super keys would be `Employee ID` and `Employee username`

A super key can also be a group of attributes, such as `Employee ID` and `Employee name` together can be used to identify a user.

This makes all of the super keys be:
`{Employee ID}`
`{Employee Username}`
``{Employee ID, Employee Username}``
``{Employee ID, Employee Name}
`{Employee Username, Employee Name}`
`{Employee ID, Employee Username, Employee Name}`

### Candidate Key
A candidate key is the smallest group of superkeys. These are:
`{Employee ID}`
`{Employee Username}`

### Primary Key
A primary key is a candidate key that is decided to be the unique identifier of each tuple in a relation. One of the above candidate keys can be used to identify the tuple.

### Foreign Key
A foreign key is an attribute of a table that is the primary key in another table. This allows a link to be made between 2 tables, and allows for a relationship.

In the below tables, employee ID is in both tables, this means that both tables can be merged together or have a relationship made.
### Composite key
A combination of two fields together can uniquely identify a record. This can be used as an alternative to a primary key,

In the below databases, `Salary ID` and `Employee ID` are the same, therefore you can use either of the two.

| Employee ID | Employee Username | Employee name |
| --- | --- | --- |
| 1 | 7528 | Steve |
| 2 | 9643 | Anna |
| 3 | 2389 | Ahmed |
| 4 | 4739 | Tina |


| Salary ID | Date | Salary | Employee ID |
| -- | -- | -- | --|
| 1 | Dec-2017 | 1500 | 1 |
| 2 | Dec-2017 | 1200 | 2 |
| 3 | Dec-2017 | 1700 | 3 |
| 4 | Jan-2018 | 1900 | 4 |

# Integrity Constraints
### Entity integrity
This rule states that every table must have a primary key field, and that the data in the primary key field bust be unique.

### Referential Integrity
This rule states that each foreign key in one table must have the same data as the primary key in another table (Or must be NULL).


# Entity relationships
### One to One:
A single record of a table is related to a single record of another table, for example, One person has one passport.

### One to many
A single record of a table is related to many records of another table, for example, one customer may have many orders.

### Many to many
More than one record of a table is related to more than one record in another table. Unfortunately, these relationships are impossible inside of a relational database. While they exist, we must resolve this into multiple one to many relationships.


# SQL Queries

In this example I have 1 sample Database:

| SalaryID | Date | Salary | EmployeeID | EmployeeUsername | EmployeeName |
| -- | -- | -- | --| -- | -- |
| 1 | Dec-2017 | 1500 | 1 | 7528 | Steve |
| 2 | Dec-2017 | 1200 | 2 | 9643 | Anna |
| 3 | Dec-2017 | 1700 | 3 | 2389 | Ahmed |
| 4 | Jan-2018 | 1900 | 4 | 4739 | Tina |

## Select query
With the SELECT query, you can select certain things:
```
SELECT SalaryID, EmployeeName
FROM SampleTbl
```
This will select the following information:

| SalaryID | EmployeeName |
| -- | -- |
| 1 | Steve |
| 2 | Anna |
| 3 | Ahmed |
| 4 | Tina |

## Select WHERE 
With the SELECT Query you can select things within certain parameters:
```
SELECT *
FROM SampleTbl
WHERE SalaryID=1
```
Will select the following information:

| SalaryID | Date | Salary | EmployeeID | EmployeeUsername | EmployeeName |
| -- | -- | -- | --| -- | -- |
| 1 | Dec-2017 | 1500 | 1 | 7528 | Steve |
## Insert into
With the INSERT query, you can add information to tables:
```
INSERT INTO SampleTbl (SalaryID, Date, Salary, EmployeeID, EmployeeUsername, EmployeeName)
VALUES ('5', 'Oct-2017', '1850', '5', '8103', 'Bob');
```
Will edit the table to look like this:

| SalaryID | Date | Salary | EmployeeID | EmployeeUsername | EmployeeName |
| -- | -- | -- | --| -- | -- |
| 1 | Dec-2017 | 1500 | 1 | 7528 | Steve |
| 2 | Dec-2017 | 1200 | 2 | 9643 | Anna |
| 3 | Dec-2017 | 1700 | 3 | 2389 | Ahmed |
| 4 | Jan-2018 | 1900 | 4 | 4739 | Tina |
| 5 | Oct-2017 | 1850 | 5 | 8103 | Bob |
## Update
Allows you to update existing records in a table:
```
UPDATE SampleTbl SET Salary='2000'
WHERE SalaryID =1;
```
Will update the tale to look like this:

| SalaryID | Date | Salary | EmployeeID | EmployeeUsername | EmployeeName |
| -- | -- | -- | --| -- | -- |
| 1 | Dec-2017 | 2000 | 1 | 7528 | Steve |
| 2 | Dec-2017 | 1200 | 2 | 9643 | Anna |
| 3 | Dec-2017 | 1700 | 3 | 2389 | Ahmed |
| 4 | Jan-2018 | 1900 | 4 | 4739 | Tina |
| 5 | Oct-2017 | 1850 | 5 | 8103 | Bob |

## Delete
Allows you to delete a record in a table
```
DELETE FROM SampleTbl WHERE salaryID='5'
```
Will update the table to look like this:

| SalaryID | Date | Salary | EmployeeID | EmployeeUsername | EmployeeName |
| -- | -- | -- | --| -- | -- |
| 1 | Dec-2017 | 2000 | 1 | 7528 | Steve |
| 2 | Dec-2017 | 1200 | 2 | 9643 | Anna |
| 3 | Dec-2017 | 1700 | 3 | 2389 | Ahmed |
| 4 | Jan-2018 | 1900 | 4 | 4739 | Tina |
