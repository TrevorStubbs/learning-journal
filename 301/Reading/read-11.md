# Read: 11 - EJS
#### 6/14/200

- [Intro To EJS](https://www.youtube.com/playlist?list=PL7sCSgsRZ-slYARh3YJIqPGZqtGVqZRGt)
- [Working With Volumes](https://developers.google.com/books/docs/v1/using#WorkingVolumes)
- [Embedded JavaScript Templating](https://ejs.co/)
- [Templating with EJS](https://scotch.io/tutorials/use-ejs-to-template-your-node-application)
- [Node-EJS GitHub](https://github.com/scotch-io/node-ejs)

## EJS - Embedded JavaScript Templating
### Setup
- `npm init -y`
- `npm i -S express cors ejs`
- `app.set('view', path.join(_dirname, 'views'));`
- `app.set('vew engine', 'ejs');`

- 3 things for EJS
    - view
    - obj
    - callback


``` JavaScript
app.get('/', (req, res) => {
  res.render('index', {
      foo: 'bar'
  });
});
```

``` HTML
<h1>Hello <%= foo %=></h1>
```
- `<%= =%>` Open and close EJS tags

### EJS Arrays
```JavaScript
app.get('/', (req, res) => {
    res.render('index', {
        people: [
            {name: 'dave' },
            { name: 'Jerry' }
        ]
    })
})
```

```HTML
<ul>
    <% for(var person of people){ %>
    <li><%= person.name %></li>
    <% } %>
</ul>
```

### If/Else EJS
```JavaScript
app.get('/', (req, res) => {
    res.render('index', {
        people: [
            {name: 'dave' },
            { name: 'Jerry' }
        ]
    })
})
```
- `=` in EJS is evaluation

```HTML
<ul>
    <% for(var person of people){ %>
        <% if(person.name === 'dave') { %>
        <li>This is definitely <%= person.name %>!!!</li>
        <% } else %>
        <li>This is definitely not Dave!!! This is <%= person.name %>.</li>
        <% } %>
    <% } %>
</ul>
```
``` JavaScript
let ejs = require('ejs');
let people = ['geddy', 'neil', 'alex'];
let html = ejs.render('<%= people.join(", "); %>', {people: people});
```

- Terminal `ejs ./template_file.ejs -f data_file.json -o ./output.html`

```HTML
<script src="ejs.js"></script>
<script>
  let people = ['geddy', 'neil', 'alex'];
  let html = ejs.render('<%= people.join(", "); %>', {people: people});
</script>
```


## Google APIs
- send a GET to: `https://www.googleapis.com/books/v1/volumes?q=search+terms`
    - query params - response `200 OK`
        - intitle: Returns results where the text following this keyword is found in the title.
        - inauthor: Returns results where the text following this keyword is found in the author.
        - inpublisher: Returns results where the text following this keyword is found in the publisher.
        - subject: Returns results where the text following this keyword is listed in the category list of the volume.
        - isbn: Returns results where the text following this keyword is the ISBN number.
        - lccn: Returns results where the text following this keyword is the Library of Congress Control Number.
        - oclc: Returns results where the text following this keyword is the Online Computer Library Center number.



