- Know what we mean by blocking and non blocking code
- understand the asynchronous nature of JavaScript
- know how the Node API handles sources of asynchronicity
- know how to use callbacks to access the result of an async funciton



# JavaScript
- JS is single threaded
- runs top to bottom
- it does one thing at a time
- although it's quick, it takes time to count to 3 billion

## Blocking code
- code that runs sequentially, lines code of code block other lines of code


## Sources of delay in processing
- I/O
	- Network requests
	- File operations
	- Database operations
	- User interactions
- Timers

```js
setTimeout(taskOne, 3000);
taskTwo()
```
taskTwo() will be run first and then taskOne() after 3000 milisecs. So i guess setTimeout is asynchronous



# Node file system
- fs.readFile()

```js
// index.js
const fs = require("fs")

function shoutedFileContents(path, callback){
	fs.readFIle(path, "utf-8", function (err, data) {
		callback(null, data.toUpperCase)
	})
}
})
```

```js
index.test.js
test("", () => {
function testCallbackFn(err, data){
	expect(err).toBe(null);
	done();
}
shoutedFileContents("./mystery.txt", testCallbackFunction)
})
```