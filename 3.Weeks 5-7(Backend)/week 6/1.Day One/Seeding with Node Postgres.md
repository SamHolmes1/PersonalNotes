- A seed function should plant the seeds of what the initial state of the database should look like, should be used on test databases. Wouldn't want to use this on a live database!
- npm install pg-format

```js
// - /db/index.js
const { Pool } = require("pg");

module.exports = new Pool();
```

- CREATE DATABASE nc_snacks before this in psql

```js
// categories.js

modules.exports = [
{ 
	category_name: 'Chocolate Bar',  category_description: "chocolate"
}

]
```

```js
// - /db/seed.js

const db = require('./index.js');
const format = require('pg-format')
const { categories } = require("./categories.js")
 

function seed(categories){

	const formatedCategories = categories.map((cat) =>
	return [cat.category_name, category_description])

	dropTables().then(() => {
		return createTables();		
	}).then(() => {
		insertCategories(categories);
	}).catch((err) => {
		console.log(err.toString())
	})
	// insert data in tables
	
}

function dropTables(){
	return db.query("DROP TABLE IF EXISTS snacks"),then(() => {
		db.query('DROP TABLE IF EXISTS categories;')
	})
	
}

function createTables(){
	db.query('CREATE TABLE categories(
		category_id SERIAL PRIMARY KEY,
		category_name VARCHAR(50) UNIQUE,
		category_description TEXT
	);').then(() => {
		db.query() // Create the snacks table in here
	}).catch((err) => {
		console.log(err.toString())
	})
}

function insertCategories(categories){
	return db.query('INSERT INTO categories 
		(category_name, categor_description)
		VALUES
		()
	')
}

seed();
```

# Warning
- 