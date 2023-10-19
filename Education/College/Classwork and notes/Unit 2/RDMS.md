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
| Normalisation | 
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

## Append
Allows you to append records from one table to another after running a SELECT query


# Normalisation
## What is it?
When considering a real life situation that you want to put into a relational database, it may be difficult to find a way to put the data into different tables in the most efficient way.
For this reason, the process of normalisation was developed to help database engineers make designs to avoid duplicated data, which will help to minimise storage requirements and help to avoid problems that occur with duplicated data.
For example, if a postcode is help on a database in 2 tables, then the customer moves house and their postcode changes, it should update in both tables.

## The process
The process of normalisation is an important part of the databased design process. The outcome of this process will be a verified database design which identifies the main structure of the database; including:
- The tables that the database will be split into
- The indexes used, including the primary, foreign and any composite keys required for the tables.
- The structure of the individual tables from which the data dictionary can be created.

## Stages of normalisation
Normalisation is a 3 stage process, which begins with raw data. This is something you may extract from a paper based system
### UNF (Un-Normalised Form)
This is before normalisation happens, and this is the un-normalised, raw data.
### 1NF (1st Normal Form)
This is the first stage, which takes the raw data and modifies its structure to meet the requirements of 1NF
### 2NF (2nd Normal Form)
The second stage modifies the 1NF structure to meet the requirements of 2NF
### 3NF (3rd Normal Form)
The third stage takes the 2NF data structure and modifies it to meet the requirements of 3NF

## Example
![[Pasted image 20231002093524.png]]
### 1NF
From the raw invoice above, you only need a select ammount of data:
- Order number
- Customer name
- Customer address
- Product ID
- Product Description
- Price
- Quantity

We don't need the calculated date (total) as databases are not for making calculations.

You need to make sure that each item is atomic (as small as it can be). For example, The customer name can be split into ('FName', 'SName')
You also need to remove repeating groups, so taht there is a data item for every record of each atrribute. For example, in the paper-based order form, order number and customer number occur just once but we need to include them in each record of our 1NF table.
Finally, we need to select a primary key (which needs to be unique). There is no one value that is unique but you can create a composite key using the Order Number and Product ID.

### 2NF
The second stage of normalisation is to modify the data to meet 2NF. if the table already has a primary key based on a single attribute, then nothing needs to be done. However if we have a  composite key we need to remove data that is dependant on just one part of the composite key to a different table.
We can remove the following;
- Product Description
- Product Price
Into their own table, with Product ID in both tables as a foreign key.

### 3NF
The final stage in normalisation is to modify the data to meet the requirements of 3NF. This requirement is that none of the non primary key attributes should depend on any other attributes. If they do, then they can be moved, leaving an attribute as a foreign key.
We can move the customer names, as they are dependant on the customer number.
# Anomalies
(TABLE FROM LAST LESSON!!!)
## Insert anomalies
To insert a new order into a database, the customers name needs to be entered, even if the customer has already placed an order. This allows for errors or inconsistencies
Another possible source of anomalies so that customers may need to enter their address for each order. With the 3NF version of the database, where toe customer details  would be in the Customer table. This means that only the Customer Number will need to show in the orders table.
Anoter issues is registering new customers, as you will eed a product ID as it is part of the composite key. That means you cannot put a null value in the Product ID attribute, and therefore its impossible to make an account without an order.

## Delete anomolies
If a customer cancels their order, then the order will be deleted. However, since that order has been deleted, you are now missing the product ID and order numbers, which are the main parts of the composite key. That means that the existance of this customer is gone.

## Update anomolies
If a customer changes their address, it will be changed on every order, this is incorrect infromation. This is avoided in 3NF as the customer details are seperate.
Another issue with the 1NF version of this database is thata product can only be in the database if it has been ordered.
## Referential integrity
One issue that occurs with a relational database system is dealing with linked records when deleting/updating a record at one end of a one2many relationship.
Consider the customer and orders relationship, one custome can place many orders and the link is made by placing the customer table's primary key attribute as a foreign key in the order tabe.
However, if a customer closes his account, there will be an order table with orders that have no customer information. These will be considered lost orders and may cause problems.
## How 2 fix
- use cascading updates where deleting records on customer table would delete records on order table automatically. microsoft access and sql server ave an option to do this, which is known as refferential integrity.

## Task
You don't want to delete all customer orders, because if there is a fraud risk there may be issues if you delete customer orders.
Some alternatives is deleting the customer account but not the orders.
You can hold order information

## Referential integrity and cascading update/delete
If you allow updates to a primary key, then anything linked to it is lost.
If you have an employee where toe primary key is the NI number, and the appraisals table has the NI number as the foreign key, but the NI number was incorrect, you would update it but then all of the appraisal records would be lost, as the NI number in the other table is changed.

## Task

Keeping employee NI numbers as a primary key is not a good idea due to possible data mis-entry
You can use an Employee ID number as the key field instead.