- Learn how functions can be returned out of functions
- Understand what closure means in javascript
- Learn how to use closure to create functions

# Closure
- Very closely tied to the rules of scope
- Happens automatically
- is a traditionally difficult concept
- Inner function remembers the scope it was declared in


```js
function makeCounter() {
	let count = 0;
	function incrementCounter(){ // Inner function
		count++;
		return count;
	}
	return incremenetCOunter
}

myCounter = makeCounter();

const output1 = myCounter(); // 1
const output2 = myCounter(); // 2


```


# Higher order function
- A function that can take another function as an argument
- A function that can return another function
- Creates a C.O.V.E (closed over variable environment)