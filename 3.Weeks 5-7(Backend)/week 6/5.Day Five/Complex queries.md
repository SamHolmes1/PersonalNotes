- revise the TDD process for creating endpoints
- Know hot to build up a complex query string
- Know the order in which SQL statemetns must be written
- Know how to prevent SQL injection by 'green-listing'


- Jest-sorted is the library that allows you to check  

```js
//app.test.js
describe("", () => {
	test("", () => {
		.get("/api/snacks")
		.expect(200)
		.then(({ body }) => {
			const { snacks } = body;
			snacks.forEach((snack) =>{
				expect(snack).toMatchObject({
					snack_id: expect.any(Number),
					snack_name: expect.any(String),
					snack_description: expect.any(String),
					price: expect.any(Number),
					category_id: expect.any(Number)
				})
			})
		})
		
	})
})

```



```js
//snacks.models.js

exports.selectSnacks = (category_id) => {
	if(category_id){
		return db
		.query()
	}
}


```

# ORder of SQL commands
SELECT
FROM
JOIN
WHERE 
GORUP BY
HAVING 
ORDER BY 
LIMIT