# Read: 06 - Node, Express, and APIs
#### 6/1/20

[An Introduction to Node.js on sitepoint.com](https://www.sitepoint.com/an-introduction-to-node-js/)

## What is Node.js
> Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine.
> Node.js is an event-based, non,blocking, asynchronous I/O runtime that uses Google's V8 JavaScript engine and libuv library.
## What is the V8
- The V8 engine is an open-source JavaScript engin that runs in Chrome and Chromium-based browsers. 
- Node is a JavaScript runtime.
## Binaries vs Version Manager
- Preferred to use a version manager so you can install multiple versions of Node and switch between them. 
- lets you set a Node version on a per-project basis.
## The Node.js way
- use `node [name.js]` to run a js file within your terminal
## Supported by Modern JS
- [compatibility table](https://node.green/)
## npm the JS Package Manager
- if installation needed
    - `npm install -g jshint`
    - use jshint to analyse your JS for errors and potential problems
## What is Node Used for
- Help automate the process of developing a modern JS app.
- Server-side applications built with JS.
- JS is single-threaded but allows for asynchronous calls. 
- Things can run while it waits for a response from a server.
- [Visual Example of How Asynchronous Works](http://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)
## Downsides?
- Single-threaded can be a problem. 
    - I/O can be completely blocked. 

## Hello, world - Server version
```JavaScript
const http = require('http');

http.createServer((request, response) => {
  response.writeHead(200);
  response.end('Hello, World!');
}).listen(3000);

console.log('Server running on http://localhost:3000');
```
- then run `node hello-world-server.js`
- navigate to `http://localhost:3000`
## What Apps
- Good for apps that require some form of real-time interaction.
- APIs where it's handling lots of I/O requests.
- Good for data streaming. 
## Advantages
- you can do everything with a single language
- natively speaks JSON