# SQLite Get Started
SQLite is a database engine that is popular for its efficiency.
It is ideal for small databases that store smaller amounts of data.

## Installation
`sudo apt install sqlite3`

## Create DB
To create a db or open an existing SQLite database use `sqlite db_name`.
If the database is not created, a new file will be created with the
db_name. However, the file will not be saved unless a query is executed.
We can run an empty query (`;`) to ensure the file is saved.

## Commands
When connected SQLite command prompt mode, mode commands are prefixed with a
period. Some useful commands:
* `.tables` - lists all tables in the database.
* `.databases` - lists all databases open in current connection.
* `.exit` - exit SQLite connection
* `.schema table_name` - presents the table schema in full. Including
  the indexes.

## Create table
`CREATE TABLE sharks(id integer NOT NULL, name text NOT NULL, sharktype text NOT NULL, length integer NOT NULL);`

In SQLite, the data types are different to MySQL, Microsoft server or
PostgreSQL whereby they use a strict typing system. SQLite uses a
dynamic typing system. This means it is the data that determines the
data type. Not the column. This allows for a column to have an integer
data type but you can store any kind of data type and SQLite will not
complain.

For more complex systems that rely on stricter data typing, SQLite is
not suitable.

SQLite has five primitive storage classes. Or rather data types.
Although storage classes are more general than data types, they are used
interchangeably.

|Storage Class| Meaning |
|---|----- |
|NULL|NULL values mean missing information or unknown.|
|INTEGER| Integer values are whole numbers (positive or
negative)|
|REAL|Real values are real numbers with devimal values that use
8-byte floats.|
|TEXT|Stores character data. The maximum lenth is unlimited|
|BLOB|BLOB stands for binary large object that can store any kind of
data.|

## Insert rows
`INSERT INTO tablename VALUES(values go here);`

## Update rows
`UPDATE tablename SET col=newval WHERE condition`

## Delete rows
`DELETE FROM tablename WHERE condition`

## Typeof
SQLite provide a `typeof()` function that checks the storage class of
a value based off of its format.

Related
  * [sqlite tutorial]("https://www.sqlitetutorial.net/sqlite-data-types/")
  * [digital ocean install]("https://www.digitalocean.com/community/tutorials/how-to-install-and-use-sqlite-on-ubuntu-20-04")

Tags:
  #SQL #Database #Tutorial
