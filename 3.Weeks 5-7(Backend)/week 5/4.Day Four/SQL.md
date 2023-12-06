- Understand that there are different types of database
- Be able to unteract with the pswl CLI
- Know how to create and delete a database using psql
- Know hot o perform CRUD operations using psql
- Know the most common postgreSQL data types
- Be able to perform operations conditionally

# Databases
- A database is a collection of information, stored electronically on a server that can be read, updated and deleted through a Database Management System(DMS)

## Non-Relational
- Also known as NoSQL
- Data is unstructured or semi-structured
- Use a variety of data models
	- Very felxible and scaleable
- MongoDB, Firebase, Amazon DynamoDB(there are many)

## Relational
- Data is Highly structured
- Data organized in tables rows and columns
	- a row is a single record
	- a column is a specific field
- Data queries are written in SQL
	- Good at describing complex relationships between data

### SQL
- Structured Query Language
	- Oracle, SQLite, PostgreSQL(There are many)
- Why SQL?
	- Time
	- Standardisation
	- Easier to go from SQL to NoSQL
- Why PostgreSQL?
	- Open source
	- Very similar syntax to other versions


# PSQL
COMMANDS MUST END WITH ;
- \\c lets us connect to a server
- \\dt shows us the tables in the database
- \\d column  will give us the column
- SERIAL defines auto incremented value, don't have to insert a value into it
```SQL
-- example.sql
DROP DATABASE IF EXISTS nc_snacks; -- Drop it if it exists

CREATE DATABASE nc_snacks; -- Recreate the database

\c nc_snacks; --Connect to the Database

CREATE TABLE vending_machines (
	vend_id SERIAL PRIMARY KEY,
	vend_location VARCHAR(50) NOT NULL,
	cost INT NOT NULL,
	date_last_stocked DATE
);

INSERT INTO vending_machines
	(vend_location, cost, date_last_stocked)
VALUES
	('leeds', 1000, '2023-01-14')
	('manchester', 1500, '2023-03-12'),
	('birmingham', 2000, '2023-04-10');

SELECT * FROM vending_machines
ORDER BY cost ASC;

UPDATE vending_machines
SET vend_location = 'cottonopolis'
WHERE vend_id = 2
RETURNING *;

SELECT * FROM vending_machines;

DELETE FROM vending_machines
WHERE vend_location = 'leeds'
RETURNING vend_location AS deleted_location;

```

- psql -f example.sql > example.txt