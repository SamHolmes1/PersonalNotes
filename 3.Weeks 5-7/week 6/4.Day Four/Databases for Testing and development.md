- Understand the reasons for test and development databases
- Know how to organise environment variables securely
- Know how to connect to different databases programatifcally


- FIrst you need to create another database in the sql file
- process.env stores environment variables
- process.env.NODE_ENV can tell you whether you're in a test environment
- Environment variables live in .env files
- These should also be added to .gitignore with .env.*

```js 
//connection.js

const { pool } = require("pg");

const ENV = process.env.NODE_ENV || "development";
const pathToEnvFile = `${__dirname}/../.env.${ENV}`
require("dotenv").config({ path: pathToEnvFile });
const PGDATABASE = process.env.PGDATABASE;
// Remove 'PGDATABASE= * ' from scripts in package.json

module.exports = new Pool();
```

1. We created two databses
2. Our listener is in a seperate file
3. We noted that jest sets process.env.NODE_ENV to "test"
4. We noted that this is undefined when jest is not running
5. we installed dotenv
6. we created 2 sets of environment variables in *.env.test* and *.env.development*
7. we created a path to the .env files which is dynamically determined by NODE_ENV/ ENV
8. We used a dotenv in index.js to load environment variables