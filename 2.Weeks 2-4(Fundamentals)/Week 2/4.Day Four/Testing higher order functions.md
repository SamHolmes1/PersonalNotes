- Know the meaning of a higher order function(HOF)
- Understand the "black box" of our current testing approach
- Understand the limitations of this approach
- Be able to take advantage of lexical scope to test HOFs
- Bonus: Know the meaning of "mocks" and "spies"


# Higher order Functions
1 Functions which take other functions as arguments(today)
2 Functions which return other functions(tomorrow)


```js
//index.js
function myForEach(arr, iteratee) {
	for(let i = 0; i < arr.length; i++){
		iteratee(arr[i]);
	}
}
```

```js
//index.test.js
const myForEach === require("index")

describe("myForEach()", () => {
	test("returns undefined", () => {
		//Arrange - setup any inputs/vars
		const nums = [2,3,5];
		const testIteratee = {} => {};
		//Act - call the function
		const output = myForEach(nums, testIteratee)
		//Assert - do the assertion
		expect(output).toBe(undefined)
	})
	test("calls the iteratee function once for each element of the array", () =>{
		//Arrange
		const nums = [2,3,5]
		let count = 0;
		const testIteratee = () => {
			count++;
		}
		//Act
		myForEach(nums, testIteratee);
		//Assert
		expect(count).toBe(3)
	})
	test("calls the iteratee with each element in the array", () => {
		//Arrange
		const nums = [2,3,5];
		const passedArgs = [];
		const testIteratee = (arg) => {
			passedArgs.push(arg)
		} 
		//Act
		myForEach(nums, testIteratee);
		//Assert
		expect(passedArgs).toEqual([2,3,5])
	})
})
```
- Lexical scope is the reason we can access count







# Current Testing approach
- input > function > output, we don't care about what is happening within the function. 