# Read: 06a - Dynamic web pages with JavaScript
## Javascript

### How to use Objects & Methods
- Typical javascript method call
- `[object].[methodname]([parameters])`
- Javascript runs where its found in HTML
    - it can be run inline `<script>[javascriptCode]</script>`
    - or it can be run from an external file
        - `<script src="[[directory/]script.js]"></script>`

### Statements and code blocks
- Each individual instruction is known as a statement
- A code block is many statements linked together.

### Comments
- use `//` to write comments on a single line
- use `/**/` to write comments on a multiple lines. 

### Variable
- A variable is a container that can temporarily store bits of data that the program needs 
- A variable can take any types.
- `var [name]` or `var [name] = [initial value]`

## Data Types
- Numeric
    - int
    - float
- String
    - letters and other characters
- Boolean (lower case)
    - true
    - false

## Escape Characters
- `\` will tell the compiler to ignore the next character

## Shorthand for creating variables
```javascript
var price quantity, total;
price = 5;
quality = 14;
total = price * quantity;
```

### Rules for naming variables
- cannot start with a number (1)
- after the first digit it can contain any symbol
- cannot use keywords/reserved words
- variables are case sensitive
- be descriptive with the var
- camelCase is used mostly in javascript
