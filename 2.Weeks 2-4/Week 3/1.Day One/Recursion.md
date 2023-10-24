- Know the definition of a recursive function
- know the 3 core components of a recursive function:
	- Base Case, recursive call, recursive step
- Understand the necessity of each of these components
- Create a recursive function
- Analyse what happens when executing a recursive function

```js
const factorial = (num) => {
	let product = 1;
	for (let i = num; i > 0; i--){
		product *= i;
	}
	return product
}
```
Requirements for a for loop:
- A point at which it must stop
- A way of approaching that point

```js
const factorial = (num) => {
	
	if(num === 1){return 1}
	return num * factorial(num - 1)
}
```

Requirements for recursion:
	- base case(a stop case)
	- a recursive call(function call)
	- recursive step(the function args)


# But why?
-  Some languages do not have for loops
- If you are traversing through nested data, sometimes there is no choice

