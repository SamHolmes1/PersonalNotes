# Where are async tasks handled?
- Node API
	- The event loop
	- Background Thread
	- Task Queue


# How can we pass data out of an asynchronous function?
- Using callbacks
	- A function that we pass in that is invoked when the async process has completed


# Why can't we return out of an async function?
- We are not in the global scope


# What pattern do we follow with callbacks?
- Error first


# Task 5
- Function will take an array and a callback
- a request should be made for each element in the array 
- it will invoke the callback with an array of the responses(order is not important)
- it there is an error on one of the calls, the response array should contain a placeholder

## What behaviours are we testing for?
- If passed an empty array callback with an  empty array
- Handles an error by adding a placeholder to the array
- callback with an array of same length
- Single item in array
- Multiple items in array
- called-back array contains the correct items


## Single item
### Inputs
- ['cute-cat'], callback

### Function
- Make a request on a path
	- `/pics/${arr[0]}`
- callback 
	- err -> innerCallback(placeholder)
	- data -> finalCallback(data)


### Output
- Array of same length(['cute-cat.jpg']) / ['placeholder.jpg']



## Multiple Items
### Inputs
- \[array of multiple items], callback


### Functions
- Declare response array
- Iterate over input array
- path, innerCallback
	- err -> push(placeholder)
	- data -> push(data)
- push to response array


### Output
- array of same length




# Example
```js
function fetchCatPics(arr, finalCallback){
	const catPics = []

	arr.forEach((cat) -> {
		request("/pics/${cat}", function (error, data) {
			if(err) {catPics.push("placeholder.jpg")}
			else{
				finalCallback(null, catPics)
			}
		})
	})
}
```

the callback must be called within the inner callback as it is async, so the final output