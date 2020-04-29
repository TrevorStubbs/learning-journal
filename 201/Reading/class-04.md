# Read: 04 - HTML Links, CSS Layout, JS Functions
#### 4/28/20

## Links
### Types of links
- Links to another website
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

## Layout 
- Block-level box
  - Starts on a new line
- Inline box
  - Is in line with the other elements

- Box inside a box
  - The outside box is called the parent
  - the inside called the child.

- Positioning Schemes:
  - Normal flow
  - Relative Positioning
  - Absolute Positioning
  - fixed Positioning
  - Floating Positioning


### Normal flow
- `position: static`
  - Each block-level element sits on top of the next.
  - this is the default so it's not necessary to use this property.
  
### Relative Positioning
- `position: relative`
  - Moves an element in relation to where it would have been in normal flow.
  
### Absolute Positioning
- `position: absolute`
  - This takes the element out of its normal flow and no longer affects the position of other elements on the page. (Acts like it's not there.)

### Fixed Positioning
- `position: fixed`
  - A type of absolute positioning that requires the position property to have a value of fixed. 
  - It keeps its position relative to the browser window.
  
### Overlapping Elements
- If boxes overlap, the elements that appear later in the HTML code sits on top of those that are earlier.
- `z - index`
  - tells the browser what is in front of what.

### Floating Elements
- allows you to take an element in normal flow and place it as far to the left or right of the containing element as possible.
- Anything else that sits inside the containing element will flow around the element that is floated. 

### Using Float to place elements side-by-side
- the float property is commonly used to achieve this.

### Clearing floats
- the clear property prevents elements, within the same containing element, should touch the left or right sides of a box
  - `left`: left-hand side of the box should not touch any other elements appearing in the same containing element
  - `right`: right-hand side of the box should not touch any other elements appearing in the same containing element
  - `both`: Neither side
  - `none`: Elements can touch each other.

### Parents of floated elements
- If a containing element only contains floated elements, some browsers will treat it as ifs 0 pixels tall.
- Old Solution: added an extra element after the last floated box (leaving and empty element in the HTML)
- New Solution: `overflow: auto` and `width:100%`

### Multi-column with floats
- Position the columns next to each other.
  - Width
  - float
  - margin

  ```CSS
  .column1 {
    float: left;
    width: 620px;
    margin: 10px;
  }
  .column2 {
    float: left;
    width: 300px;
    margin: 10px;
    }
  ```

  ```CSS
  .column1, .column2, .column3 {
    width: 300px;
    float: left;
    margin: 10px;}
  ```

### Screen Sizes
- What device is your user going to use?
- Phone
  - 960x640
- Tablet
  - 1024x768
- 13" Laptop 
  - 1280x800
- 27" Monitor
  - 2560x1440

- Standard Desktop version page size
  - 960-1000 pixels wide.

### Fixed width layouts
- Design does not change with the user changes browser window size. (fixed pixel numbers)
  - Advantages 
    - Pixel values are accurate
    - Designer has greater control over the appearance
    - Can control the lengths of lines of text
    - size of an image will always remain the same
  - Disadvantages
    - Can end up with big gaps around the edge
    - If the screen is a much here resolution the page can look smaller and text can be harder to read
    - If a user increases font sizes, text might not fit into the allotted spaces
    - Can take up more vertical space.

### Liquid Layouts
- Stretch and contract as the user changes browser window size (use of percentages)
  - Advantages
    - Page expand to fill the browser window
    - a user with a small window wont have to scroll to the side to see all the content
    - its tolerant of users change of font size
  - Disadvantages
    - page can look different from what you expected
    - if the window is wide the text can stretch
    - If narrow words can be squashed
    - images can overflow


### Layout Grids
- Many designers use a grid structure to help them position items on a page.
  - Grids set consistent proportions and spaces between items. 
  - Creates a continuity
  - Help users predict where to find info on subsequent pages.
  - Makes it easier to add new content to the site in a consistent way
  - Helps people collaborate [example](http://www.htmlandcssbook.com/code-samples/chapter-15/grid-layout.html)

### CSS Frameworks
- Aims to make your life easier by providing the code for common tasks
  - Advantages
    -  Save time from rewriting code
    - Have been tested across different browsers
  - Disadvantages
    - Often require that you use class names that only control the presentation of the page
    - Often contain more code than you need for your page.
- [960.gs](https://960.gs/)
- [bootstrap](https://getbootstrap.com/docs/3.4/css/)

### Multiple Style Sheets
- possible reasons to use multiple
  - 1 sheet to control fonts and colors
  - 1 sheet to control layouts
- Can use 1 `<link>` tag in HTML and in the main CSS use `@import url("");`
- or you can use multiple `<link>` in the HTML

## Functions 86-99
- You can group expressions together into a function

- Here is an example
```javascript
function updateMessage(){
    var el = document.getElementById('message');
    el.textContent= msg;
}
```
- You can activate the function at any time by calling it name
```javascript
updateMessage();
```

- How to write a function
```javascript
// format is function keyword
// function name ()
// statements;
function [functionName]([parametersIfNeeded]){
    [expression];
    [return] [returnValue]; // not required if the function doesn't return anything
}
```

- How to call a function
```javascript
//call the function's name followed by '();'
[functionName]([arguments]);
```

- if you need a value out of a function you need to use the `return` keyword at the end

### Anonymous Functions & Function Expressions
- Expressions produce a value. If a function is placed where a browser expects to see an expression then it gets treated as an expression
```JavaScript
var area = function(width, height){
  return width * height;
};

var size = area(3,4);
```

### Immediately Invoked Function Expressions (IIFE)
- This can prevent variable names from conflicting with each other.

```JavaScript
var area = (function() {
  var width = 3;
  var height = 2;
  return width * height;
}());
```
- When to use these
  - Functions that only need to be run once
    - As an argument when a function is called.
    - To assign the value of a property to an object
    - In event handlers and listeners to perform a task when an event occurs
    - To prevent conflicts between 2 scripts that might use the same var name.

### Variable Scope
- Local
  - a var created inside a function can only be accessed from inside that function
- Global
  - a var outside a function that can be used anywhere.

### Memory & Vars
- Global vars take more memory.
- Each var that is declared takes up memory. 
  - the more memory you use the slower the webpage will run.

- Try to avoid naming collisions
  - keep things as local as they can be

## [Reasons for Pair Programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)
- 2 heads are better than one.
### How does it work
- a driver
  - typing, and handling the mechanics of coding
- a navigator
  - uses their words to guide the Driver but doesn't provide direct computer input.
### Why?
- Listening: hearing and interpreting the vocab
- Speaking: using the correct words to communicate an idea
- Reading: understanding what written language intends to convey
- Writing: producing from scratch meaningfullness

1. Greater Efficiency: 2 people working on the same code will catch mistakes in the making. Pair programming can take longer but produces higher-quality code. (less time debugging/troubleshooting).
1. Engaged collaboration: More engaged and more focused. It's harder to procrastinate in a team. Easier to know when to ask for help.
1. Learning from fellow students: Everyone has a different approach to solving problems. It allows students to see how others work and learn from each other.
1. Social Skills: talking is hard. This helps us practice communication.
1. Job interview readiness: if you can talk code with your peer you can talk code with an interviewer. 
1. Work environment readiness: CF grads are a leg up on the CS students since we know how to pair program.