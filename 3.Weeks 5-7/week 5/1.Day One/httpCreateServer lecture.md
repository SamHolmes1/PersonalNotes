- Create an application that will accept requests from an outside source
- Respond with appropriate data based on the type of request

```js
const http = require("http")
const fs = require("fs/promises")

function handleRequest(request, response){
	const { method, url } = request; // Object destructuring
	if (method === 'GET' && url === '/') {
		const responseBody = { message: "hello folks!" };
		response.setHeader("contentType", "application/json");
		response.statusCode = 200;
		response.write(JSON.stringify(responseBody));
		response.end();
	}else if(method === 'GET' && url === "/cats"){
		fs.readFile(`${__dirname}/cats.json`).then((data) => {
			const cats = JSON.parse(data);
			console.log(cats);
			const responseBody = { cats: cats };
		})
	}
}

const app = http.createServer(handleRequest);

app.listen(80);
```

- Node will not exit the program while there is a pending async task.
- Listen() is an async task
- http.createServer takes an async callback function
- Response is an object that is handled by node in C++
- response.statusCode is likely a setter function behind the scenes but looks like using a property normally
- response.write() is an async function that splits everything up into packets
# What's going on 
## Call stack
- Global execution context

## Thread
- First thing we have is require()
- http.createrServer(handleRequest())
- app.listen(port)


## Variable Environment
- http createServer()
- handRequest()
- app

## Node API
- C++ features of the node API
### List of async tasks
- When we invoke createServer() it returns an object for us that allows us to access the C++ features
- It is listening on the port we give it and it won't be removed from the list of async tasks and therefore node will not stop running

## Making a request
- The request gets sent to our modem via our OS
- Out async task will emit an event that we can that handle
- This gets put onto the task queue
- Node then invokes our handler callback function