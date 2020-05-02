# Read: 06 - JS Object Literals; The DOM
- The problem domain
- Ch3: Object Literals pp100-105
- Ch5: DOM 183-242

## Understanding the Problem Domain
- It's hard to learn more than 1 thing at once. 
- The guy uses the same problem when he is learning a new technology
    - I have been thinking of a timer app
    - or a dice rolling app

### Why are Domains Hard?
- It's hard to put together a puzzle if you don't know what it looks like.
- We need to find a way to see the big picture so we can put the pieces together

### Programming is Easy(ish) if you Understand the Problem Domain
- It's easy to build in an old waterfall approach
    - Tougher in agile

### What to do about it
- Make the problem domain easier
- Get better at understanding the PD.
- If it's to difficult to understand break it apart

## JS Object Literals
### What is an Object
- Objects group variable and functions to create a model of something.
    - Variables are called properties
    - Functions are called methods
- Object names are called **keys**

### Literal Notation for Object creation Example

```JavaScript
var hotel = {
    name: 'Airbnb',
    rooms: 4,
    booked: 2,
    gym: true,
    roomTypes: ['twin', 'double', 'master'],
    checkAvailability: function(){
        return this.room - this.booked;
    }
}
```

### Accessing an object and using Dot Notation
- `[objectName].[propertyName];`
- `[objectName].[methodName()];`

```JavaScript
var hotelName = hotel.name;
var roomsFree = hotel.checkAvailability();
```

- you can access properties (not methods) using brackets
    - `var hotelName = hotel['name'];`

### Creating an Object: Constructor Notation
```JavaScript
var hotel = new Object();
hotel.name = 'Quay';
hotel.rooms = 40;
hotel.booked = 25;
hotel.checkAvailability = function(){
    return this.room - this.booked;
}
```

### Updating an Object
- `hotel.name = 'Park';`
- `hotel['name'] = 'Park';`

---

## The DOM 183-242
- The Document Object Model specifies how browsers should create a model of an HTML page and how JS can access and update the contents of a page.
- Each object represents a different part of a page.
- DOM is an API (application programming interface.)

### The DOM Tree
- a model of a web page.
- Document Node: Represents the entire page.
- Element Node: Describe the structure of and HTML page
    - Once you find the element you want then you can access its text and/or attribute nodes.
- Attribute Node: Gives access to the attribute of an element
- Text Node: Give access to the text of an element

![The DOM](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1280px-DOM-model.svg.png)<sub>[wikipedia](https://en.wikipedia.org/wiki/Document_Object_Model)</sub>

### Working with the DOM Tree
1. Locate the node that represents the element
1. use its text content, child elements, and attributes.

- Access the Elements
    - Select an individual node
        - `getElementById()` HTML
        - `querySelector()` CSS
    - Select multiple nodes
        - `getElementByClassName()`
        - `getElementByTagName()`
        - `querySelectorAll()`
    - Traversing between Element nodes
        - `parentNode`
        - `previousSibling/nextSibling`
        - `firstChild/lastChild`

- Work with those Elements
    - Access/Update Text
        - `nodeValue`
    - Work with HTML content
        - `innerHTML`
        - `textContent`
        - Can create new nodes, add nodes to a tree and remove nodes from a tree
            - `createElement()`
            - `createTextNode()`
            - `appendChild()/removeChild()`
    - Access or update attribute values
        - `hasAttribute()`
        - `getAttribute()`
        - `setAttribute()`
        - `removeAttribute()`

### Caching DOM Queries
- Methods that find DOM elements are called queries.
- Sometimes you need to query the same element multiple times.
    - use a var to store the result of the query.
    - Some people will call this 'storing an element in a variable'

### Accessing Elements
- DOM queries may return only 1 element or they may return a NodeList (collection of nodes).
    - If a method can return more than one node it will return a NodeList (in the form of an array). You will then need to select the node you are looking for using an index.
    - Finding the quickest way to access an element in your page will make the page seem faster/responsive.

### Element Selecting Methods:
- Single Node Returns
    - `getElementById('[id]')` - Selects the element that has specified [id]
    - `querySelector('[css selector]')` - Uses CSS selector syntax that would select 1 or more elements. This method returns only the 1st of the matching elements.
- 1 or more element returns - produces a collection
    - `getElementByClass('[class]')` - Select the elements of that class - produces a collection
    - `getElementsByTagName('[tagName]')` - Selects all the elements of the page with that tag - produces a collection
    - `querySelectorAll('[css selector]')` - Uses CSS selector syntax to select one or more elements and returns all of those that match. - produces a collection
- NodeList is a collection of element nodes. THey look like arrays but they are collections. 
- Live NodeList- when your script updates the page. Typically faster to generate than static NodeLists.
- Static NodeList- when you script updates the page, the NL is not updated to reflect the changes made by the script.

### Selecting an item from a NodeList
- `item()` method - 
- `array[0]` syntax - faster

### Selecting Elements using CSS Selectors


### Can use a loop to repeat actions for the entire NodeList

### Looping Through the DOM
### Traversing the DOM
- WHen you a have an element node, you can select another element in relation to it:
    - `parentNode`
    - `previousSibling`
    - `nextSibling`
    - `firstChild`
    - `lastChild`
- Whitespace Nodes 
    - Most browsers treat WS between elements as a text node.
    - can make using theses transversal properties not work. 
    - you can strip all the whitespaces out but that would make your code harder to read.
    - jQuery has ways of dealing with this