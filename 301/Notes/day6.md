# Day 6
#### 6/8/20

# Review
- default order in flex is `0`
- `node [jsfile name]`

# Setting up a Server
- npm init
- npm i -S express
- const express = require('express');
- require('dotenv').config();
- const app = express();
- npm i -S dotenv

```JavaScript
'use strict';

// express library is our server
const express = require('express');
// initializes our express library into our variable called app
const app = express();

// dotenv lets us get our secret from our .env file
require('dotenv').config();

// bring in the PORT by using process.env.variable name
const PORT = process.env.PORT || 3001;

//serve static file from a public file (not route)
app.use(express.static('./public'));

// serve home route
app.get('/', (request, response) => {
  // to the terminal
  console.log('I am the Home Route (I am in the terminal)');
  // to the browser
  response.send('I show up on the browser on the Home route');
})

// serve the public route
app.get('/public', (request, response) => {
  console.log('I am the public route (I am in the terminal)');
  response.send('I show up in the browser on the Public route');
});

// turn on the server
app.listen(PORT, () =>{
console.log(`listening on ${PORT}`)
});
```

### How to access the server in the terminal
- npm start
- node server.js
- nodemon

- Backend version of an event listener.
```JavaScript
response.send (routeName, (req, res) =>{

});
```

## Routes
- request
- response

## errors
- 200 - everything works fine
- 404 - not found
- 500s - server error 
    - 
```JavaScript
    try{
        // code from within the app.get
    } catch(err){
        console.log('ERROR', err);
        response.status(500).send('sorry, we messed up');
    }
```

```JavaScript
// City Explorer Demo
// request is the input
// response is the output
app.get('/location', (request, response) => {
  // query: {city: 'seattle'}
  console.log(request.query.city);
  let searchQuery = request.query.city;

  let geaData = require('./data/location.json');

  let returnObj = new Location(search_query, geoData[0]);

  console.log(returnObj);

  // let returnObj = {
  //   search_query: search_query,
  //   formatted_query: geoData[0].display_name,
  //   latitude: geoData[0].lat,
  //   longitude: geoData[0].lon
  // };

  response.status(200).send(returnObj);
});

// {
//   "search_query": "seattle",
//   "formatted_query": "Seattle, WA, USA",
//   "latitude": "47.606210",
//   "longitude": "-122.332071"
// }

function Location(searchQuery, obj){
  this.search_query = searchQuery;
  this.formatted_query = obj.display_name;
  this.latitude = obj.lat;
  this.longitude = obj.lon;
}

```

### CORS - body guard
    - bring in CORS libarry
    - npm i -S cors
``` JavaScript
cons cors = requires('cors');
app.use(cors());
```

- backend library 
    - `let geoData require('./data/location.json')`


