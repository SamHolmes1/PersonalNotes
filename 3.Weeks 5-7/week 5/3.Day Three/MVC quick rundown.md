My internet broke so i missed this lecture

- The Model handles the actual data and does stuff with it
- The Controller handles the request and response data
# Example


```js
//server.js

const express = require("express")
const { getSingleOWner } = require("./controllers/owners.controllers")

const app = express();

//Middleware
app.use(express.json()) //JSON formatting on our objects

app.use((req, res, next) => { // Request Logging
let date = new Date(Date.now())
fs.appendFile(`${__dirname}/log.txt`, `METHOD: ${req.method} URL:${req.url} TIME: ${date.toString()} \n`, "utf-8")
next()
})

app.get("/api/owners/:id", getSingleOwner) // request single owner by id

app.listen(9090, () => {
	console.log("Server is listening on port 9090")
})
```

```js
//owners.controllers.js

const { getOwnerById } = require("../models/owners.models")

exports.getSingleOwner = (req,res) => { // export the function
	const id = req.params.id
	getOwnerById(id).then((owner) => { //call the model with a .then()
		res.status(200).send(owner); // the model returns a promise
	}).catch((err) => { // Catch any errors thrown by the model
		res.status(404).send(err.toString())
	})
}
```

```js
//owners.models.js
// This is the end of the require chain
const fs = require("fs/promises")

exports.getOwnerById = (id) => {
	return fs.readFile(`${__dirname}/../data/owners/${id}.json`, (err, data) => {
		if(err){throw new Error("Owner does not exist")}
	}).then((owner) => {
		const singleOwner = JSON.parse(owner)
		return singleOwner
	})
}
```