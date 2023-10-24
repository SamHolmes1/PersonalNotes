- Understand the distinction between Function and Object-Oriented Programming
- Know hot to create a factory function
- Understand the use of this
- Know what we mean by binding
# Functional vs OOP
- A paradigm is a mode of doing something
## Functional
- Functions have been the main building blocks of our code
- Functions are 'first class citizens' and can be higher order
- Emphasises the use of pure functions and avoids mutation
## OOP
- Objects are the main building block of our code
- They can contain data and behaviours
- The data contained in objects is inherently mutable
# OOP
## First Two pillars of OOP

### Abstraction
- Simplifies complex systems by hiding implementation
- Functions or objects can be used to achieve this
- Abstracted code is modular

### Encapsulation
- Data and methods are combined into a single object
- Methods define how the data is interacted with

## Washing machine analogy

### Abstraction
- Provide inputs, e.g detergent, laundry
- performs specific actions without us knowing about the underlying processes
### Encapsulation
- Machine has internal data, e.g drum speed, water temperature
- We alter these via methods that control panel provides us 

# Examples
## Without OOP
```js
function makeCounter() {
	let count = 0;
	function incrementCount(){
		count++;
		return count;
	}
	return incrementCount;
}
```


```js
function makeCounter() {
	let count = 0;
	function incrementCount(){
		count++;
		return count;
	}
	function getCount(){
		return count;
	}
	const counter = {};
	counter.incrementCount = incrementCount;
	counter.getCount = getCount;
	return counter;
}

const myCounter = makeCounter();
console.log(myCounter.incrementCount())
console.log(myCOunter.getCount)
```

- Arrow functions and function declarations use the `this` keyword differently