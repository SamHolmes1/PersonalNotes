- Understand how JS uses prototype objects in OOP
- Understand how instances share methods from their prototype


# The final two pillars of OOP
## Inheritance
- An object can inherit properties and methods from another object
- This relationship is hierarchical i.e parent/child

- The array object comes with a prototype object that contains all of the methods for arrays.

- Prototype is an object so it can inherit from another prototype - a prototypal chain


```js
let arr =m [1,2,3];
console.log(arr.hasOwnProperty("length"));
```

- The above code works because \[Array does not contain hasOwnProperty-> the array prototype does not contain hasOwnProperty -> The object prototype does contain hasOwnProperty]

```js
const myPrototype = {
	method1: () => {},
	method2: function(){}
}

function factoryFunction(){
	const myObj = Object.create(myPrototype);
	myObj.propertyOne = 0;
	return myObj;
}

```
