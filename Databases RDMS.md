## Defenition:
A database used to keep information in tables, which are joined into datasets.

# Types of RDMS/RDBMS
| | Desktop | Server |
|--------|  --------- |---------|
| Example | Microsoft Access | Oracle, MySQL |
| Usage | Local/Development | Websites/large projects |
| Features | Guis, Wizards| Tuis, Large databases, Accessible from anywhere |

# Pros and cons
|  | Desktop | Server |
| ------ | ------ | -------|
| Pros| Cheap, Easier to use for less IT literate users | Not scaleable |
| Cons| Lesser access | Expensive |

# Terminology
| Term | Defenition |
| -----| -------|
| Relations | Table, grid made of rows and columns. |
| Tuples | Record, row in database, Each tuple is one item (e.g. one book in a bookstore DB) |
| Attributes | Information on a record, such as the price of a book|
| Domains | The requirement for the attribute - data type, and other rules - E.G. `(int, 1, 10)`
| Cardinality | The uniqueness of an atribute, Repeated values would have a "Low cardinality" where as non-repeated values would have Cardinality

# Example table
| ISBN | BOOK TITKE | GENRE | PRICE | PUBLISHER ID |
| -----| ------| ------| -----| -----|
| 95-XXXX-XXX-X | EXAMPLE TITLE 1 | TECHNOLOGY | £14.99 | 123|
| 98-XXXX-XXX-X | EXAMPLE TITLE 2 | TECHNOLOGY | £19.99 | 321|

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
|[[#Symbols \|Join]] | Combine [[#Terminology \|Attributes]] from two [[#Terminology \|Tables]] | Join two [[#Terminology \|Tables ]] into a dataset|
Going back to our example DB, using the `Select` operator to search for a Publisher ID of "123" Would yield this response:

| ISBN | BOOK TITKE | GENRE | PRICE | PUBLISHER ID |
| -----| ------| ------| -----| -----|
| 95-XXXX-XXX-X | EXAMPLE TITLE 1 | TECHNOLOGY | £14.99 | 123|
