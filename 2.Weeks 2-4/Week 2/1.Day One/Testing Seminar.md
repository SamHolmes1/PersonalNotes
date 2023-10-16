- Know how to use TDD when testing a function's behaviour
- understand why TDD is important 
- know how to setup a test suite using npm and jest
- know what is meant by the red green refactor cycle
- Make sure to .gitignore node_modules/

npm init -y(says yes to all params)


```js
//get-middle-char.js
function getMiddleCHar(inputString){
	return ""
}

module.exports = getMiddleChar
```


```js
//get-middle-char.test.js
const getMiddleChar = require("../get-middle-char")

describe("getMiddleChar", () => {
	test("When given an empty string, should return an empty string", () => {
		expect(getMiddleChar("")).toBe("")
	})
	test("when passed a single char, return that char", () => {
		expect(getMiddleChar("a")).toBe("a")	
	})
})

```

- Describe can take an anonymous function or an anonymous arrow function
- Remember to make sure the test fails first
