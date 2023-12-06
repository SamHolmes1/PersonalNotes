- Understand what a pure function is
- know how to test for mutation of objects (and nested Objects) with jest
- Know how to test for newness of objects returned out of functions with jest

# Pure function
- A function that doesn't have any negative side effects, doesn't touch the input.
- The function should return a new object reference, does not mutate the original input
- ONLY when dealing with non primitives

# Testing pure functions

```js
describe("function()", () => {
	test("should return a new object", () => {
		expect(function(input)).not.toBe(input)
	})
})
```

- Useful for testing references to make sure the function is pure

# Creating deep copies