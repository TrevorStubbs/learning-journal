# Read: 02 - HTML Text, CSS Introduction, and Basic JavaScript Instructions
#### 4/26/250


## Text
- Structural Markup: elements that you can use to describe both heading and paragraphs
- Semantic markup: provides extra information (such as where emphasis is placed, that something is a quotation, the meaning of acronyms, etc.)

### Structural Markup:
### Headings
- `<h1>` heading element (block level)
    - Can go all the way down to `<h6>` 

### Paragraphs
- `<p>` paragraph element (block level)
    
### Bold & Italic
- `<b>` bold element
- `<i>` italic

### Superscript & Subscript
- `<sup>` superscript (ie exponent<sup>2</sup>)
- `<sub>` subscript (ie citation<sub>1</sub>)

### Whitespace
- When the browser comes across 2 or more spaces next to each other, it will only display 1 space.
- Line breaks are represented by a single space as well.

### Line breaks & Horizontal rules
- `<br>` is a line break
    - it will instruct the browser to start on the next line
- `<hr>` basically a line break with a horizontal line.
<hr>

### Semantic Markup:
### Strong & Emphasis
- `<strong>` indicates strong importance
    - usually represented at bold
- `<em>` emphasizes a subtle change in the meaning of a sentence
    - usually represented as italic.

### Quotations
- `<blockquote>` used for longer quotes that take up an entire paragraph.
    - browseres tend to indent the contents of a `<blockquote>`.
- `<q>` used for shorter quotes that sit within a paragraph.

### Abbreviations & Acronyms
- `<abbr title=""></abbr>` Used to define an abbreviation or an acronym but only show it if the user mouses over the word.
- `<acronym title=""></acronym>` old used in HTML4. Modern HTML5 only uses the `<abbr>`
```HTML
<p><abbr title="Professor">Prof</abbr> Stephen
 Hawking is a theoretical physicist and
 cosmologist.</p>
<p><acronym title="National Aeronautics and Space
 Administration">NASA</acronym> do some crazy
 space stuff.</p>
 ```
 <p><abbr title="Professor">Prof</abbr> Stephen
 Hawking is a theoretical physicist and
 cosmologist.</p>
<p><acronym title="National Aeronautics and Space
 Administration">NASA</acronym> do some crazy
 space stuff.</p>

 ### Citations & Definitions
 - `<cite>` will indicate where the citation is from
    - usually seen as italic
- `<dfn>` used to show where you are defining a term
    - Some browsers will render this as *italic* (safari and chrome won't)
- `<address>` used to specify either an email address or a physical address
```HTML
<address>
<p><a href="mailto:homer@example.org">
 homer@example.org</a></p>
<p>742 Evergreen Terrace, Springfield.</p>
</address>
```
<address>
<p><a href="mailto:homer@example.org">
 homer@example.org</a></p>
<p>742 Evergreen Terrace, Springfield.</p>
</address>

### Changes to content
- `<ins>` used to show where something is inserted
- `<del>` used to show where something is deleted
- `<s>` indicates something that is no longer accurate or relevant (but should not be deleted)
```HTML
<p>It was the <del>worst</del> <ins>best</ins> idea
 she had ever had.</p>

<p>Laptop computer:</p>
<p><s>Was $995</s></p>
<p>Now only $375</p>
 ```
 <p>It was the <del>worst</del> <ins>best</ins> idea
 she had ever had.</p>
<p>Laptop computer:</p>
<p><s>Was $995</s></p>
<p>Now only $375</p>

---

## Intro to CSS
- Think inside the box

### Everything is a box
- Each element in HTML is a [box](http://www.htmlandcssbook.com/code-samples/chapter-10/thinking-inside-the-box.html) that CSS can individually style.
    - Example Styles:
        - Boxes: Width and height, Boarders (color, width and style) background color and images position in the browser window.
        - Text: Typeface, size, color, italics, bold uppercase, lowercase,  small-caps

### Block Level vs Inline Level
- Block level elements (by default) take up the entire width of it's parent container and each new element tag will start a new line.
    - `<h1>, <p>, <div>, <ul>, <li>, <nav> and <header>`
- Inline Elements do not start on new lines.
    - `<span>, <a>, <em>, <code> and <button>`
        
### How CSS Code is Written
The format of CSS code
- A CSS rule contains 2 parts: a selector and a declaration.
```CSS
p {
    font-family: Arial;}
```
- Inside the curly brackets are 1 or more declarations. A declaration is made up of 2 parts: a property and a value.

```CSS
h1, h2, h3{
    font-family: Arial;
    color: yello;}
```
---
### Getting CSS into your site
You have to tell your HTML document that you are using CSS. There are 2 ways of doing that: Internally or Externally.
- External CSS file: use the `<link href="[CssFileLocation]" type="text/css" rel="stylesheet">` tag in the head tag of your html docutment.
- Internal (inline) CSS formating: use the `<style type="text/css">` tag followed by your css coding (don't forget to close the tag (`</style>`)).
        - Only do this if you have only 1 page to your site or that you need a special rule that only applies to this page.

### CSS Selectors
CSS selectors allow you to target rules to specific elements in an HTML document. 
Selector | Example | Meaning
--- | --- | ---
Universal Selector | `*{}` |Applies to all elements in the document.
Type Selector | `h1, h2, h3 {}` | Matches element names
Class Selector | `.[classname] {}` or `[tag].[classname] {}` | Matches to elements that has the same class name. (Uses the period `.`)
ID Selector | `#[idname] {}` | Matches to elements that has the same id name. (Uses the hash `#`)
Child Selector | `[parentelement]>[childelement] {}`, ie `li>a {}` |  Matches to an element that is direct child of another
Descendant Selector | `[outerElement][innerElement]{}`, ie `[p a {}]` | Matches to elements that is a descendant of another specified element
Adjacent Sibling Selector | `[firstElement]+[firstTargetElement]{}`, ie `h1+p{}` | Matches an element that is the next sibling of another
General Sibling Selector | `[firstElement]~[targetElement] {}`,ie `h1~p {}` | Matches an element that is a sibling of another, although it doesn't have to be the direct preceding element

### How CSS cascades
- Last rule
    - If 2 selectors are identical, the latter will take precedence.
- Specificity
    - The more specific rule will take precedence
- Important 
    - Tagging something as important will make it take precedence.
    ```CSS
    p.b {
        color: blue !important;}
    ```
- Inheritance
    - nested elements will inherit properties from their parent elements.

### Why External sheets are better
- It allows all your sheets to pull from a single CSS file.
    - maintains site cohesion
    - less jarring for the reader.
- Less work for the client's computers.
    - You may have a good net connection but it doesn't mean they do.
---

## Basic JavaScript Instructions
### The Language
1. Vocabulary
    - Words the comp understands
1. Syntax
    - How you put word together

- Computers are the dumbest
    - they have to be told exactly what to do
    - they can to infer anything
    - you have to 'think' like a comp

- Sketch out the tasks in a flowchart

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

### Data Types
- Numeric
    - int
    - float
- String
    - letters and other characters
- Boolean (lower case)
    - true
    - false

### Var - Number
- Numbers are not surrounded by quotation marks.
- If you use the `+` on 2 varables that are numbers you'll get the sum of those 2 numbers
```JavaScript
x = 2;
y = 3;
z = x + y; // z is now == 5
```

### Var - String
- Strings are surrounded by quotes. 
    - it doesn't matter in JavaScript if you used single or double quotes. They just have to be the same.
    - Good `'Hello World' "Hello World"`
    - Bad <s>`"Hello World'`</s>
- When `+` is used on strings it will concatenate the 2 strings together.
```JavaScript
x = "hello";
y = "World";
z = x + y; // z is now helloWorld
```

### Using Quotes in a String
- Whatever you want inside the string use the other ones to define the string.
```JavaScript
"My Mom's"
```
- Or you can use the escape character (`\`)
    - This tells the compiler/browser to ignore the next symbol
```JavaScript
'My Mom\'s"
```

### Var - Boolean
- In JavaScript booleans are lowercase
    - `true` or `false`

### Variable definition shorthand
```JavaScript 
//Place values when a var is defined 
var price = 5;
var quantity = 14;
var total = price * quantity;
```
```JavaScript
//Define vars then add their values
var price, quantity, total;
price = 5;
quantity = 14;
total = price * quantity;
```
```JavaScript
//Define and add values to the vars all in 1 line (not clean code imo)
var price = 5; quantity = 14;
total = price * quantity;
```
### Changing the value of the var
- use the assignment operator `=` to change the value.

### Rules for naming variables
- cannot start with a number (1)
- after the first digit it can contain any symbol
- cannot use keywords/reserved words
- variables are case sensitive
- be descriptive with the var
- camelCase is used mostly in javascript

### Arrays
- Arrays store a list of values
```JavaScript
var colors;
colors = ['white', 'black', 'custom'];
```
- Arrays are an index data type
    - Starts at index 0
- To access the first element if the above array use: `colors[0]`
- To return the number of items in the above array use: `colors.length`
- To change an element in the above array use: `colors[2] = 'red'`

### Expressions and Operations:
- An expressions evaluates into a single value.
    - `var color = 'beige';`
    - `var area = 3 * 2;`

### Operators
    - `=` assignment operator
    - `+` arithmetic operator
    - `'[char]'` string operator
    - `>` Comparison operator
    - `&&` logical operator

### Arithmetic Operators
Name | Operator | Purpose
--- | --- | ---
Addition | `+` | Adds one value to another
Subtraction | `-` | Subtracts 1 value from another
Division | `/` | Divides two values
Multiplication | `*` | Multiplies 2 values
Increment | `++` | Adds 1 to current value
Decrement | `--` | Subtracts 1 from current value
Modulus | `%` | Divides 2 values and returns the remainder

### String Operator
- Turn anything into a string by wrapping it in `""`.

---

## Decisions and Loops 145-162
### Comparison Operators:
- `==` is equal to
- `===` is strict equal to
- `!=` not equal to
- `!==` strict not equal to
- `>` greater than
- `<` less than
- `>=` greater than or equal to
- `<=` less than or equal to

### Logical Operators
- `&&` and
- `||` or
- `!` not

### `if` statements
- The `if` statement evaluates a conditions and if the statement if `true` it will run the statements in the subsequent blocks.
```JavaScript
if (age > 50)
{
    console.log("You're old");
}
```
- if the statement is not true then the program will skip this code block.
- If you want to have the program do something else instead then add a `else` block after the `if` block
```JavaScript
if(age>50){
    console.log("You're old");
}
else {
    console.log("You're too young");    
}
```
---

## How to write a git commit message
- Preferred: Concise and consistent 
- A well crafted Git commit message is the mest way to communicate context about a change.
- Lack of use leads to unstructured and inconsistent messages.
- **Style**: Markup syntax, wrap margins, grammar, capitalization, punctuation.
- **Content**: What kind of info should the body of the commit message contain?
- **Metadata**: How should issue tracking IDs, pull request numbers, etc be referenced?

### 7 rule of a great Git Commit message
1. Separate subject from body with a blank line
1. Limit the subject line to 50 characters
1. Capitalize the subject line
1. Do not end the subject line with a period
1. Use the imperative mood in the subject line
1. Wrap the body at 72 characters
1. Use the body to explain what and why vs. how