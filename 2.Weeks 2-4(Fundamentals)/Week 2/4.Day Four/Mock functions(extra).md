# Mock functions
- Functions for the purpose of testing
- Allow us to capture and use and assert against, data or information or function behaviour unrelated to the behaviour going on inside the function body
- Test behaviours, information, unrelated to function body behaviour
   - How many times the function has been called
   - it's parameters
- Allows us to spy on other functions


```js
//index.js
function myForEach(list, iteratee){
	for (let i = 0; i < list.length; i++){
		iteratee(list[i]);
	}
}

module.exports = myForEach;
```


```js
const myForEach = require("index")

describe('mock function', () => {
	test('assert the number of times a function has been called', () => {
		const mockFn jest.fn()
		mockFn()
		mockFn()
		expect(mockFn.mock.calls.length).toBe(2)
	})
	test('asserts the number of times a function has been called using jest custom matchers', () => {
		const mockFn = jest.fn()
		mockFn()
		expect(mockFn).toHaveBeenCalledTimes(1);
	})
	test('asserts the arguments we expect to pass', () => {
		const mockFn = jest.fn()
		mockFn(1);
		expect(mockFn).toHaveBeenCalledWith(1);
	})
	test('can be used to test behaviour of the forEach away from implementation', () => {
		const mockFn = jest.fn();

		const input = ['a', 'b', 'c'];

		myForEach(input, mockFn)

		expect(mockFn).toHaveBeenCalledTimes(3);
		expect(mockFn).toHaveBeenCalledWith('a');
		expect(mockFn).toHaveBeenCalledWith('b');
		expect(mockFn).toHaveBeenCalledWith('c');
	})
	test('can be used to mock and test existing behaviours', () => {
		//Math.random() - really hard to test
		
		const mockMathRandom = jest.spyOn(Math, 'random')
		mockMathRandom.mockImplementation(() => {
			return 0.1;
		})
		mockMathRandom.mockRestore();
	})
})
```





# Useful stuff
- `console.log(mockFn.mock) // returns a bunch of data about the function`
- `mockMathRandom.mockRestore();// restores a function back after implementation` 