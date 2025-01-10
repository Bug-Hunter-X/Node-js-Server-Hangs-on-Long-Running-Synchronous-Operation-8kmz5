# Node.js Server Hang - Synchronous Operation

This repository demonstrates a common issue in Node.js where a long-running synchronous operation within the request handler blocks the event loop, causing the server to hang and become unresponsive to new requests.

## Bug Report
The `server.js` file contains a simple HTTP server that simulates a long-running task (a 5-second delay) within the request handler.  This prevents the server from handling any subsequent requests during this time, effectively making it unresponsive.

## Solution
The `serverSolution.js` file shows the solution using asynchronous operations and promises or async/await to prevent blocking the event loop.

## How to Reproduce
1. Clone this repository.
2. Navigate to the directory.
3. Run `node server.js`.
4. Try to access the server using a browser or `curl`.  Note that after the first request, subsequent requests will hang until the first request completes.
5. Repeat steps 3 and 4 with `node serverSolution.js` to see the corrected behavior.

## Conclusion
This example highlights the critical importance of using asynchronous programming in Node.js to maintain responsiveness and avoid blocking the event loop.