# Objectives
- Know what a module is 
- know how to share data across JS files using module .exports

# Modules

- A module is just a file
```js
console.log(module); // returns a unique object for this file
```
- You can export things from a file like so:
```js
module.exports = thingToExport;
```
- You can import things like so:
```js
const varName = require("./path/to/file");
```
- You can export multiple things
```js
module.exports = {var1: data1, var2: data2};
```
- You can then import it and use it like this
```js
const importedFile = require("./file1")
console.log(importedFile.var1, importedFile.var2);
```
- Exporting functions
```js
function sayHello(name){
	return `Hello ${name}`;	
}

module.exports = {sayHello: sayHello}
```
- And then in the other file
```js
const importedFile = require("./file1")

const importedFunction = importedFile.sayHello;
console.log(importedFunction("sam")); // expected output "Hello Sam"
```

- Under the hood, require runs the whole file, that means any console.log() or any other functions that are being called in global scope