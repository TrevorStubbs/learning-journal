# Read: 05 - Heroku Deployment
#### 5/30/20

- [Heroku: Getting Started with Node](https://devcenter.heroku.com/articles/getting-started-with-nodejs)
- [Deploying a Simple Blog to Heroku](https://howtonode.org/deploy-blog-to-heroku)

## Heroku Setup and Deployment
### Setup
- `heroku login`
### Deployment
- `git clone [repoULR]`
- `cd [repoFolder]`
- `heroku create`
- `git push heroku master`
- `heroku ps:scale web=1`
- `heroku open`
- `heroku logs --tail`
## Node.js and Heroku
- `node server.js`
- create project directory
- create `package.json`
- run `npm install`
- create a 404 function to handle 404 errors
- define `sendPage()` function
- `http.createServer(<some code here>).listen(3000)`
- create the index.html
- run the server locally
    - `node server.js`
- git init AC heroku create P
- ensure an instance is running `heroku ps:scale web=1`
- name the server `heroku apps:rename [name]`
- `heroku open`