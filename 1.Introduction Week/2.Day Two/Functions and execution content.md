# Learning Objectives
- Understand the benefits of using functions
- know how to invoke functions in JS
- know how to declare functions in JS
- understand the basics of JS interprets code
- understand the concept of the call stack, the thread and the variable environment


## Node
- Node is a runtime environment for JavaScript
- Under the hood, Node uses the chrome V8 engine

## JavaScript
- JS has a single thread of execution
- it is read line by line
- Synchronously - one piece at a time.
- Doesn't have a main() function

## Execution context

- The function definition has parameters / placeholders
- The function call takes an argument or an actual
- ^ subtle but useful difference

```js
function Example(value){
	//Code Body
	return newValue;
}

const data = example(value);

```

- When you run this code the whole of the function is called

- Need to look into first-class citizen
### Variable environment
- This is where our created variables/data are stored
- When functions aren't being called they are stored in the variable environment

### Thread
- JavaScript can only perform one thing at a time
- Expressions are evaluated here
- Functions run in the thread

- Functions have their own variable environment when called

### Call Stack
- Functions are put here to be run in the thread
- Since it's single threaded, it uses a stack, almost like an execution order
- the call stack is last in first out
### Global variable
- Global methods that are always available to us  

## Functions

### Expression
- const functionName = () => {}

### Declaration
- function sayHello () {}
