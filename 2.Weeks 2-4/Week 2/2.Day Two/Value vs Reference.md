- Understand the difference between value and reference
- Understand what it means for a data type to be immutable
- Understand how non primitive data types are held on reference
- Understand how objects can be mutated
- Understand the difference between toBe and toEqual
# Data types
## Primitive
- string, number, boolean, undefined, null, symbol, Bigint
- Primitive data types are immutable, you can not change part of their value
```js 
let message = "hello world";
message[0] = 'H'
console.log(message) // Will return "hello world"
```
- Reassigning a variable is possible though
```js 
let value = 1;
value = value + 1;
console.log(value) // will return 1

value = true;
console.log(value) // will return true;
```
- primitives are compares by their value
- primitives are passed by value, not reference. They cannot be passed by reference.
## non-Primitive
- Object; Array, Function
- non-Primitives are mutable
```js
const doggo = { name: "Obi"}

doggo.age = 5

doggo.age++;

console.log(doggo) // return {name:"obi", age:6}
```
- Objects are passed by reference rather than by value
```js
const objectOne = {
	value:5
}
const objectTwo = {
	value:5
}

console.log(objectOne === objectTwo) // returns false, comparing memory addr not // value
const myObject = objectOne;

console.log(myObject === objectOne) // returns true as objectOne was passed by 
//reference

myObject.value = 12;

console.log(objectOne) // {value : 12}
console.log(myObject) // {value : 12}
```
- This behaviour is the same for arrays and pushing to copies of arrays.
```js
arrayOne = [1,2,3,4,5]
arrayTwo = [...arrayOne] // Creates a shallow copy
```


# Jest Testing
```
expect(value).toBe(value) // This is strict equality
expect(value).toEqual(value) // Checks if these objects look the same
```
- You should use .toEqual for comparing the shape of non primitives
- You should use .toBe for comparing primitives
