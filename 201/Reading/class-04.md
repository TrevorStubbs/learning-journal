# Read: 04 - HTML Links, CSS Layout, JS Functions
#### 4/28/20

## Links
### Types of links
- Links to another websitd
- Links to another page within a website
- Links to another part of the page you are currently looking at
- Links that open in another browser window
- Links that start up your email application and address a new email

### The Anchor tag
- The `<a>` (anchor) tag is used to create a link.
- The `<a>` tag takes a reference to where you want to send the user.
- Between the tags is words or symbols used for the user to click to send them to the destination. Known as the link text.
- `<a>` tags need to be closed 
- The `href` can be the URL of the next page in your site, or the URL of the site you are trying to send the user, or the class/ID of the element on the page you want to user to see.

### Links to another website
```HTML
<a href="https://www.google.com">Google</a>
```
- you can have the new page opened up in a new window using the `target ="_blank"` property and attribute
```HTML
<a href="https://www.codefellows.org" target="_blank">Code Fellows</a>
```

### Links to another page within a website
```HTML
<!-- Table of contents -->
<p>
  <ul>
    <li><a href="index.html">Home</a></li>
    <li><a href="about-us.html">About</a></li>
    <li><a href="contact.html">Contact</a></li>
  </ul>
</p>
```

### Links to a specific part of the same page
```HTML
<!-- Table of contents -->
<h1 id="top">Film-Making Terms</h1>
  <a href="#arc_shot">Arc Shot</a><br />
  <a href="#interlude">Interlude</a><br />
  <a href="#prologue">Prologue</a><br /><br />
<!-- Destinations -->
  <h2 id="arc_shot">Arc Shot</h2>
  <p>words words words words words words words words words </p>
  <h2 id="interlude">Interlude</h2>
  <p>words words words words words words words words words words words </p>
  <h2 id="prologue">Prologue</h2>
  <p>Words words words words words words words words words </p>
<p><a href="#top">Top</a></p>
```

### Email Links
- you can use an `<a>` tag to have the user's email application open and address a new email to a specific email address.

```HTML
<a href="mailto:jon@example.com">Email Jon</a>
```
### Directory Structure
- On larger websites it's a good idea to organize code by placing the pages of each different section into a new directories.

## Layout 358-404
