- Be able to query an SQL database from a Node.js application
- Be able to set up a connection pool
- Understand concept of SQL injection
- Be able to use dynamic database query parameters wuthout making queries vulnerable

# Client-Server relationship
- Client makes a request to server -> Server Handles request -> Server sends back response.
- Node-Postgres is a node module that allows us to access a Postgresql database

# MVC Recap
- The Controller handles the client request and the send data to the model
- The Model handles any operations that need to be done based on the controllers output

# Node-Postgresql
- In order to connect to a server you can use a pool or a client. A client only handles one request at a time whereas a pool can handle multiple.

```js
process.env //Gives us access to environment database
```
- When running the file you must include env variables such as: 
```sh
PGDATABASE=mydatabase PGPASSWORD=mypassword node index.js
```
- the way to sanitize input is using the query values parameter
```js 
const { Pool } = require('pg')

const pool = new Pool();

pool.query('SELECT * FROM database WHERE id=$1', [Id]) // it is not zero indexed
```