# Self Learning
- Express is a web app framework that makes creating servers much nicer to work with.
- Here's an example express server(I think)
```js
const express = require ('express');
const app = express();

app.get('/', (req, res) => res.send('Hello world'))


app.listen(8080 () => {
	console.log('Server running on port 8080')
})
```

# Learning Objectives
- Know what expres is nad how it relates to http.createServer
- Be able to create an express erver
- Know how to handle incoming request data
- Understand how to access parameters and queries from the URL
- Understand what we mean by a RESTFUL api

# Recap
- We created a server using the node http module
- Routing requests required us to manually check the URL and http method - intensive
- Headers are mostly set manually - a pain
- Request and response bodies must be stringified/parsed
- We had to manually handle data packets
- A lot of boiler plate code

# Express
- Express is minimalist, Can't do anything that http.createServer can't do for us
- uses httpCreateServer under the hood
- It extends the request and response objects
- Add more methods and properties that make development nicer 

## Express Vs http.createServer
- Routing is declarative
- Managers headers more automatically
- Handles stringification and parsing for us
- Handles data Packets for us
- Code is more concise


# REST API
- REST - Representation State Transfer
- It should have a uniform interface
- Shouldn't be using verbs in our paths
- should have parametric endpoints

# Examples
- Express will response.end() automatically for you
- We can call app.use and pass it middleware functions from express
```js
const express = require("express");
const fs = require('fs/promises')

const app = express();

app.use(express.json());

app.get("/", (req, res)=>{ // app.get() defines a get request event 
	const responseBody = { message: "hello folks!" };
	res.status(200).send(responseBody);
})

app.get("/dogs", (req, res) => {
	console.log(req.query); //returns { query: data }
	fs.readFile(`${__dirname}/dogs.json`).then((data) => {
		const dogs = JSON.parse(data);
		res.status(200).send({ dogs })
	})
})

app.get('/dogs/:userDefinedID', (req, res) => {
	console.log(req.params)//returns { userDefinedID: data }
	res.status(403).send({ message: "Forbidden"})
})

app.post("/dogs", (req, res) => {
	const newDog = req.body;
	fs.readFile.then((data) => {
		//data parsing
	}).then(() => {
	res.status(201).send({dog: newDog})
	}).catch((err) => {
	console.log(err)
	})
})

app.listen(9090);
```
- Express will default send a 404 if it cannot find specified resource


# Nodemon
- Nodemon watches for changes in the source and restarts the server
- `npm install nodemon -D` -D indicates dev dependency
- in package.json in the scripts object `"dev": "nodemon server.js"`
- and when you want to run it, run node server.js dev