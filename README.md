# Express Starter Template

This is a brief document that goes over the steps needed to set up a basic Express application.

## Steps

1. `mkdir project-name` - create the project on your local computer
2. `cd project-name` change directories into your project
3. `git init` create a new git repository for this project
4. `npx gitignore node` create a pre-built .gitignore file for node
5. `npm init -y` create a package.json file with all defaults answered yes
6. `touch index.js` create a root file
7. `npm i express` install the express package
8. `mkdir api` create folder for server file
9. `touch api/server.js` create server file
10. In the server.js file, add the sanity check server code

```js
// Import express package
const express = require("express");

// Call express to initialize server
const server = express();

// Use built in middleware to parse incoming JSON payloads
server.use(express.json());

// Get request to root with obligatory message
server.get("/", (req, res) => {
  res.status(200).json({ message: "Hello World" });
});

// Export the server
module.exports = server;
```

11. In index.js, add the following code:

```js
// Require server
const server = require("./api/server");

// Set up port for production by bringing in process.env
const port = process.env.PORT || 5000;

// Bind and listen for connection on defined port
server.listen(port, () => console.log(`Server listening on ${port}`));
```

12. `node index.js` run the server as a sanity check
