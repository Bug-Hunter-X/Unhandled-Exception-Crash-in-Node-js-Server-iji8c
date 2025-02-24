# Unhandled Exception Crash in Node.js Server

This repository demonstrates a common error in Node.js applications: an unhandled exception within an asynchronous callback causing the server to crash. The `bug.js` file showcases the problematic code, while `bugSolution.js` provides a corrected version using error handling.

## Bug

The `bug.js` file creates a simple HTTP server.  In the request handler, a `setTimeout` function simulates an asynchronous operation that randomly throws an exception. Because this exception is unhandled, it causes the Node.js process to terminate.

## Solution

The `bugSolution.js` file addresses the problem by wrapping the asynchronous operation in a `try...catch` block. This handles the exception gracefully, preventing the server from crashing.  A more robust solution might include logging the error, sending an error response to the client, or implementing a more sophisticated error-handling strategy depending on the application's needs.

## How to reproduce

1. Clone this repository.
2. Run `node bug.js`. You will observe the server crashing intermittently.
3. Run `node bugSolution.js`. The server will remain running, even if the simulated error occurs. 
