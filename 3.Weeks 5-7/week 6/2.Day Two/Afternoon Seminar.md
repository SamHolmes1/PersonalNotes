- Make sure to use app.use(express.json()) to handle incoming requests that have bodies.

```js

beforeEach(() => {
	return seed()
})

afterAll(() => {
	return db.end()
})


describe("POST /api/snacks", () => {
	test("201: responds with the new snack", () => {
		const newSnack = {
			snack_name: "cheetos",
			snack_description: "cheesy",
			price: 50000,
			category: "crisps"
		};
		return request(app)
			.post("/api/snacks")
			.send(newSnack)
			.expect((response) => {
				console.log(response.body)
				expect(response.body.snack).toEqual({snack_name: "cheetos",
				snack_description: "cheesy",
				price: 50000,
				category_id: 5;
				})
			})
	})
})
```

```js
//model

exports.insertSnack = (body) => {
	const { snack_name, snack_description, snack-description, price, category_id}
	returb db.query ('INSERT INTO snacks ..... VALUES ($1, $2, £3) RETURNING *')
}
```
- Jest has a beforeEach() it takes a callback and in the callback you can run the seeding function to recreate the database
