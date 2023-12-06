- Understand the different types of raletions betweern data
- Know how to use idfferent JOINS in SQL
- Know what a junction table is and when to use one
- Know how to use an aggregate function in SQL queries


# SQL
- It is on us to make sure we create catagories and fields with correct spelling.
- One to many relationship - A single source of truth that many items refer to.
- SERIAL types do not have to remain unique, PRIMARY KEY makes it unique.
- `category_id INT REFERENCES categories(category_id)` when i put data into category_id, it must exist in the foreign table too. 

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

CREATE TABLE categories(
	category_id SERIAL PRIMARY KEY,
	category_name VARCHAR(50),
	category_description TEXT
);

CREATE TABLE snacks (
	snack_id SERIAL PRIMARY KEY,
	snack_name VARCHAR(50),
	snack_description TEXT,
	price INT,
	category_id INT REFERENCES categories(category_id) 
);


INSERT INTO categories
	(category_name, category_description)
VALUES
	('chocolate bar', 'yummy choccy'),
	('biscuit', 'good to dunk'),
	('drink', 'thirst quenching'),
	('fruit', 'healthy choice'),
	('crisps', 'great in a sandwhich')

INSERT INTO snacks
	(snack_name, snack_description, price, category_id)
VALUES
	('boost', 'the best chocolate bar', 100, 1),
	('Kitkat', 'Based', 150, 1),
	('hobnobs', 'a delicious biscuit', 175, 2),
	('apple', 'keeps the doctor at bay', 200, 4),
	('water', 'The healthy option', 75, 3)

CREATE TABLE vending_machines_snacks(
	snack_id INT REFERENCES snacks(snack_id),
	vend_id INT REFERENCES vending_machines(vend_id)
);

INSERT INTO vending_machines_snacks
	(snack_id, vend_id)
VALUES
	(1, 2),
	(1, 3),
	(1, 4),
	(2, 2),
	(2, 3),
	(2, 4),
	(3, 7),
	(3, 6),
	(3, 5),
	(3, 3);

--SELECT snack_name, category_id FROM snacks;

--SELECT category_id, category_name FROM categories;

SELECT snacks.snack_name, categories,category_name FROM snacks
INNER LEFT JOIN categories
ON snacks.category_id = categories.category_id;

SELECT vending_machines.vend_location, snacks.snack_name
FROM vending_machines
JOIN vending_machine_snacks
ON vending_machines.vend_id = vending_mchines_snacks.vend_id
JOIN snacks
ON snacks.snack_id = vending_machine_snacks.snack_id;


SELECT vending_machines.vend_location, 
COUNT(vending_machines_snacks.snack_id) AS number_of_snacks FROM
fvending_machines JOIN vending_machines_snacks
ON vending_machines.vend_id = vending_machines_snacks.vend_id
GROUP BY vending_machines.vend_location;

```

- Categories(one) and snacks(many) have a one to many relationship

- LEFT JOIN gives all the data on the left table
- RIGHT JOIN gives all the data on the right table
- FULL OUTER gives everything

- Need to look into COUNT and aggregate functions


# DELETE
if you want to make sure the deletion applies to foreign keys you have to do the following:


```SQL
CREATE TABLE books_genres(
	genre_id INT REFERENCES genres(genre_id) ON DELETE CASCADE,
	book_id INT REFERENCES books(book_id) ON DELETE CASCADE
);
```
Make sure that you add the ON DELETE CASCADE statement in the CREATE TABLE statement.