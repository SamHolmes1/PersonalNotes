Kill me
# Recap
## Where are async tasks handled
- node API
	- background thread
	- event loop
	- task queue
## Why can't we return out of an async function
- We are not in global

## How can we pass data out of an async function?
- Using callbacks
	- a function that we pass in that is invoked when the async process has been completed 

## What pattern do we follow with callbacks
- error first

# Info
- When the async function has been completed, all the code in the callback function will be executed


# First example - single request

## Inputs
- inputArray, finalCB

## Function
- path = inputArray[0]
- request(path, innerCB)
	- if(err) -> finalCB(null, \[placeholder.jpg])
	- else(finalCB(null, \[data]))


## Output
- \[outputArray]

# Second example - multiple requests
Function specification:
- Takes an array and a callback
- makes a request for each element in the given array 
- should callback with a complete array of responses(order unimportant)
- If there is an error on one of the requests calls, it should not callback with an error but insert a placeholder instead


## input
- inputArr, finalCB
## Function
- declare an array to collect responses
- iterate over inputArr
- path = inputArr\[index]
- request(path, innerCB) x2
	- if err -> push placeholder into response array
	- if no error -> push data into response array
## Output