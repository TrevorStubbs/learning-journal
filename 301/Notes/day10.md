# Day 10 
#### 6/12/20

# Web Request response cycle -WRRC
- A client the requester
- Server is the responder

- HTTP - stateless protocol - no knowledge of previous requests

- REST - Representational state transfer
    - RESTful verbs/actions to apply state to HTTP
        - GET
        - POST

- 3 parts to every request
    1. method
        - get
        - post
        - put
        - delete
    1. Body
        - main
    1. Header
        - meta info about the request
            - API keys
            - type of data
            - time stamp
            - address

- 3 parts to every response
    1. body
    1. header
    1. status

- package.json - holds reference to dependencies

- `process` is the highest level
    - .env is just below `process`

- curl command line URL

states of a promise
- pending - waiting
- resolved - 
- rejected - 

- Database is a persistance layer

- REST -> representational state transfer -> POST / GET / PUT / DELETE
- CRUD -> database Interactions -> CREATE/READ/UPDATE/DELETE
- FORMS -> REST -> CRUD
``` JavaScript
app.get('/url', (req,res) => {
    client.query('SELECT * FROM whatever')
    .then(data => res.json(data))
});

app.post('/url', (req,res) => {
    client.query('INSERT * FROM whatever')
    .then(data => res.json(data))
});
```

- 6 welcome to node
- 7 work with routes
- 8 work with persistance
- 9 

- set the server
- spin up the server
- then build the routes

- superagent - info request engine
    - make any sort of REST request

- .query returns a promise object
    - .then pulls it out of an object
 
- `.` says its an object

- module.exports = {name: 'cool'}

# Virtual White Board
- Problem domain
- Ask questions
    - new array or in place?
- Inputs/Outputs
    - in - array
    - out - new array
- Visualization
- Edge Cases
- Algorithm
- pesudo code 
- code it out
- debug 
- optimize

# The callstack
- MVC - Model View Controller
    - Location route Example
        - View - front end
        - Controller - server
        - Model - database
