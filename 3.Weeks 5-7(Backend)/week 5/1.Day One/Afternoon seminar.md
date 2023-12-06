- trying to build a restful api. Making sure everything is standardized
```js
const http = require("http")
const fs = require("fs/promises")

const server = createServer((request, response) => {
	if(request.url === "/api/cats" && request.method === 'POST'){
		let body = '';
		request.on('data', (packet) => {
			body += packet.toString()
		})
		request.on('end', () => {
		const parsedNewCat = JSON.parse(body)
			fs.readFile(`${__dirname}/cats.json`, "utf-8").then((fileCats) => {
				const parsedOGCats = JSON.parse(fileCats)
				parsedOGCats.push(parsedNewCat);
				return parsedOGCats;
			}).then((catsToWrite) => {
				const stringCats = JSON.stringify(catsToWrite, null, 2)
				fs.writeFile(`${__dirname}/cats.json`, catsToWrite, "utf-8")
			}).then(() => {
				response.setHeader("Content-Type", "application/json");
				response.statusCode = 201;
				response.write(JSON.stirngify([cat: parsedNewCat]));
				response.end();
			}).catch((err) -> {
				console.log(err)
			})
		})
	}
})

server.listen(8080)

```


- in insomnia, you can select JSON when making a POST request