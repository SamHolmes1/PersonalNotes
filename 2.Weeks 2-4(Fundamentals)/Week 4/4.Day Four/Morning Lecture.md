- Understand the client-server model
- Know what we mean by request and response
- Know the CRUD methods used when requests are made to a URL
- Understand in what form data is sent
- Know how to manipulate data that we want to send or receive

- A list of HTTP statuses can be found at https://http.dog/ or https://http.cat/
- An API is a collection of tools that allow different apps to communicate with each other

- JSON is the predominant way of sending objects over the internet, but they are sent in string format and must be parsed when received


# Client-Server model
- Client makes a request to the server - needs a URL,HTTP Method, Headers, \[body](if needed)
- Server send a response back to the client - Body, Headers, HTTP Status code, 
- Everything is likely to be sent in multiple packets

# Protocols
- http, https, ip, ftp, tcp, udp, smtp, pop3
- Protocols are a set of rules and conventions that allow for standardised communication

# Predictability
- connection loss, Physical limitations, Latency, bad actors, server faults, traffic, packet loss, security layers
- Many things can stop our data from arriving


# Anatomy of a URL(Uniform Resource Locator)
- {protocol}://{Domain name}/{path}{query}

# CRUD/methods
## Create
- HTTP POST
## Read
- HTTP GET
## Update
- HTTP PUT/PATCH
## Delete
- HTTP DELETE

# Convert String to JSON
```js
const jsonObi = '{"name":"obi", "age":"6"}';

const parsedObi = JSON.parse(jsonObi);

prasedObi.favFoov = "sardines";

const updatedObi = JSON.stringify(parsedObi);
```