# Node.js Server Unresponsiveness Under Load

This repository demonstrates a common issue in Node.js servers: unresponsiveness under heavy load.  The example simulates a scenario where requests take a long time to process, potentially leading to a backlog and server hang.

## Problem

The provided `bug.js` file creates a simple HTTP server.  However, it introduces a 5-second delay in responding to each request.  Under high load, this delay causes a queue of pending requests. If the server doesn't handle concurrency and errors well, it becomes unresponsive.

## Solution

The `bugSolution.js` file addresses this issue by utilizing the `cluster` module for improved concurrency and includes robust error handling. This prevents server hangs by creating worker processes to manage requests concurrently and gracefully handle potential exceptions during processing.