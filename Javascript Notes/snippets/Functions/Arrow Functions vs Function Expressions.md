- Arrow function expressions
```js
const array = [1,2,3,4,5]

console.log(array.map((element) => element * 2)) //Output [2,3,4,5,6,8,10]
```

- Function expressions
```js
const getRectangleArea = function (width, height) {
	return width * height;
};

console.log(getRectangleArea(5,10)) // Output 50
```