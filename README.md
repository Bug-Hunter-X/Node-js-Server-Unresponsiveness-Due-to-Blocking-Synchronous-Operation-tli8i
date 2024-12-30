# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js servers: unresponsiveness due to blocking synchronous operations within the request handler.  The `server.js` file contains a server that simulates a long-running task. This causes the server to hang and not respond to subsequent requests.

The solution, demonstrated in `serverSolution.js`, uses asynchronous operations or worker threads to avoid blocking the main event loop.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository directory.
3. Run `node server.js`.
4. Open multiple browser tabs and attempt to access `http://localhost:3000`. You'll observe that after the first request, subsequent requests will hang.

## Solution

The solution involves offloading the long-running task to an asynchronous operation, as demonstrated in `serverSolution.js`.