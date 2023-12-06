- Understand how integration testing differs from unit testing
- Understand how to use Supertest to test end-points

# Testing Recap - What is it?
- Identify and prevent bugs
- Ensure correct functionality
- Validate changes to our codebase
- Provide a source of documentation
- Help to break down complex problems
- GIve us confidence in our code

# Unit testing VS Integration testing
## Unit Testing
- Tests a small unit of code such as individual functions or method
- units of code tested in isolation
- ensures that each unit of code produces the expected output when procided a given input
## Integration Testing
- Tests interactions between different parts of the code
- Tests functionality of an application which utilises multiple units of code
- Detects defects that arise due to interactions between them

# What to test
- For each endpoint, what happens when we make a request
- We recieve a response and can check for:
	- Status Code
	- Response Body
	- Error Handling

# GET /api and Supertest
- Responds with a JSON object containing an okay message
- When setting a test script, make sure to set the PGDATABSAE environment variable 

```js
//app.js
const express = require("express");
const { getApi } = require("api.controllers")
const { getSnackById } = require("snacks.controllers")


const app = express();

app.get("/api", getApi);

app.get("/api/snacks/:id", getSnackById);


module.exports = app;
```


```js
//app.test.js
const request = require("supertest")
const app = require("../app")

describe('GET /api', () => {
	test('200: responds with an okay message', () => {
		return request(app) //Arrange
		.get("/api") //Act
		.expect(200) //Assert with supertest
		.then(({ body }}) => {
			expect(body.msg).toBe("all okay!")
		})
	})
})

describe('GET /api/snacks/:id', () => {
	test("200; responds with an indivudual snack", () => {
		return request(app)
			.get("/api/snacks/1")
			.expect(200)
			.then(({ body.snack })).toMatchObject({
				snack_id: 1,
				snack_name: "boost",
				snack_description: "the best chocolate bar",
				category_id: 1
			})
	})
})

```

```js
//api.controllers.js

exports.getApi = (req, res) => {
	res.status(200).send({});
}
```

```js
//snacks.controllers.js
const { selectSnackById } = require("snacks.models")
exports.getSnackById = (req, res) => {
	const { id } = req.params;
	selectSnackById(id).then((snack) => {
		res.status(200).send({ snack })
	})
}
```

```js
//snacks.models.js
const db = require("../db/index")

exports.selectSnackById = (id) => {
	return db.query(`SELECT * FROM snacks WHERE snack_id = $1`, [id])
	.then(({ rows }) => {
		return rows[0];
	})
}
```


- You can return an async process in jest and it will wait for it to complete. Ensure that you return the promise