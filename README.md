# Unresponsive Node.js Server: Synchronous Long-Running Task

This repository demonstrates a common Node.js error: an unresponsive server caused by a long-running synchronous operation that blocks the event loop. The `server.js` file contains the buggy code, while `serverSolution.js` provides a corrected version using asynchronous operations.

## Problem

The original server code performs a 5-second CPU-intensive task synchronously within the request handler. This blocks the event loop, preventing it from processing other requests and leading to an unresponsive server.  Subsequent requests will hang.

## Solution

The solution involves refactoring the long-running task to use asynchronous operations.  This allows the event loop to remain responsive even while the task is running.  The solution demonstrates a simple example, however in a real application, more sophisticated task handling (using libraries like worker_threads for CPU bound tasks) might be necessary.

## How to run the example

1. Clone this repository.
2. Navigate to the directory.
3. Run `node server.js` (buggy version) or `node serverSolution.js` (fixed version).
4. Access the server in your browser at `http://localhost:3000`.
5. Observe the response time and behavior.