- Understand what a middleware function is
- Understand how to write middleware in express
- KNow which errors to handle and how
- Understand when errors are thrown and when they are not
- Know how to pass errors along the middleware chain
- Be able to extract error handling away from app.js

# Middleware
- A function that exists in the middled of the request and response cycle.
- Has access to the req and res object and the next middleware function.


{Connection dropped here}

# Error handlings
```js
throw new Error() // can't be used async?

return Promise.reject() // Can be used async?
```


- Do this at the end and maybe extract out these callback functions into seperate files
```js
app.use(errorHandleCallback)
app.use(errorHandleCallback)
app.use(errorHandleCallback)
```