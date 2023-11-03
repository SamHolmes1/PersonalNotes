- Know what an API is
- Know how to make a GET request to an API using node's https module
- No testing at all today
# What is an API
- application programming interaface
- Service that acts like a bridge enabling the different systems to talk to each other
- i.e. an external client can make a request to an API to access data stores elsewhere

- Any good API should have good docs on how to use it

# Node
Node has a https module for making requests

```js
const options = {
	hostname: "itunes.apple.com",
	port: 81, // This has a default and normally doesn't need to be set
	path: "/search?term=devilman",
	method: "GET"
}

const req = https.request(options, (res) => {
	let body = ""
	console.log(res)
	res.on('data', (packet) => {//Packet will be hex, convert using toString()
		body += packet.toString()
	})
	res.on('end', () => {
		console.log(body)
	})
})

req.end();
```

- Must make sure to end the request outside of the body of the request.