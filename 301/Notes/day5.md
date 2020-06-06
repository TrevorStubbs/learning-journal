# Day 5 -
#### 6/5/20

## 

- global vars at the top
- construction next
- prototypes
- helper functions
- event handlers
- event listeners

## Servers
- Something that serves files
- Web Request Response Cycle - WRRC

## Node
- Node Package Manager - NPM

## Express Node
- `npm init`

``` JavaScript
// This links the file to the server
const express = require('express');
const app = express();
// TODO Ready this

``` 
- `npm install -S express` or `npm i -S express`
- `-S` locks in the versions

- package-lock.json the version of npm when it was installed.

- to start the server `npm start`

- `nodemon` like live-server for the back end.

- `.env` - secrets `PORT=3000'`
- `.env` - is a secret keeper

```JavaScript
const express = require('express');
const app = express();

require('dotenv').config();

// use the static files from /public to populate the server
app.use(express.static('./public'));

const PORT = process.env.PORT;

// app.get('/', function( req, res) {
//   response.send('Hello World');
// });

// app.get('/bananas', (req, res) => {
//   response.send('I am bananas about bananas');
// });

// Turns on the server
app.listen(PORT, () => {
  console.log(`listening on ${PORT}`);
});

// app.listen(3000);

```
- `npm i -S dotenv` to make env work

- add `.env` to the git ignore



