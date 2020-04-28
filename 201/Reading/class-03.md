# Read: 03 - HTML Lists, CSS Boxes, JS Control Flow
#### 4/27/20

## Lists
- There 3 major types of lists in provided by HTML
- Ordered Lists: Numbered lists
- Unordered Lists: Bullet lists
- Definition lists: List made up of a set of terms with their definitions

## Ordered lists
- `<ol>` to create an ordered list
- `<li>` to add an element to the ordered list

## Unordered List
- `<ul>` to create and unordered list
- `<li>` to add an element to the unordered list

## Definition List
- `<dl>` to create a definition list
- `<dt>` to add a term to the list
- `<dd>` to add a definition to the previous `<dt>` element

## Nested List
- You can place a list within a list
```HTML
<ol>
  <li>Plants</li>
    <ul>
      <li>Trees</li>
      <li>Bushes</li>
    </ul>
  <li>Animals</li>
    <ul>
      <li>Cats</li>
      <li>Dogs</li>
      <li>lizards</li>
    </ul>
</ol>
```
<ol>
  <li>Plants</li>
    <ul>
      <li>Trees</li>
      <li>Bushes</li>
    </ul>
  <li>Animals</li>
    <ul>
      <li>Cats</li>
      <li>Dogs</li>
      <li>lizards</li>
    </ul>
</ol>

---

## Boxes
- Control the dimensions of the boxes
- Create borders around boxes
- Set margins and padding for boxes
- show and hide boxes

### Box Dimensions
- You can define a box either by pixels or by percentages
- percentages provides for a dynamically sized website.
```CSS
div.box {
  height: 300px;
  width: 300px;  
}
```
or
```CSS
div.box{
  height: 50%;
  width:70%;
}
```

### Min max Dimensions
- If you want to use percentages but also prevent the box from getting to large or to small you can use the `min-` or `max-` property

```CSS
#p1 {
  min-width: 450px;
  max-width: 700px;
  min-height: 400px;
  max-height: 600px;
}
```

### Overflow
- This property tells the browser what do to if the content contained in a box is larger than the box itself.
- `overflow: hidden;` simply hides any extra content
- `overflow: scroll;` adds a scrollbar to the box so that users can scroll to see the missing content (can be annoying)

## Border, Margin, Padding
![Border, Margin, padding](https://i.pinimg.com/originals/61/f2/71/61f271bb01d3b693943cae6ca63ec311.png)<sub>© ava.Java.com</sub>

1. Border: Separates the edge of a box from another
1. Margin: Sits outside the edge of the border. Adding margin can add a gab between to border lines.
1. Padding: Space between the border and the contents of a box.
    - Adding padding can increase the readability of the contents.

- The space between 2 boxes is called white space.

### Border attributes
- `border-width` defines the borders thickness
  - Can be defined as:
    - `thick`, `medium` or `thin`
    - or pixel size ie `2px`
      - if you want all sides of the border to be the same thickness define 1 attribute
      - or you can define each side by defining 4 attributes

```CSS
p {
  border-width: thick;
}
p {
  border-width: 2px;
}
p {
  border-width:1px, 4px, 12px, 4px;
}
```
- `border-style` controls the style of the border.
  - `solid`, `dotted`, `dashed`, `double`, `groove`, `ridge`, `inset`, `outset`, and`hidden/none`
- `border-color` changes the borders color. 
- `border` is shorthand for all the border properties. (I don't think its very clean)

```CSS
p {
  border: 3px dotted blue;
}
```

## Padding
- Allows you to specify how much space should appear between the content of an element and its border.
## Margin
- Controls the gap between boxes. 

## Centering Content
- Use `left-margin:auto` and `right-margin:auto`
- Need to set the width of the box or the box will take the full width of the page.
- Older browsers need the text to be aligned to center as well.
  - use this on the box not the content

## Change inline/block
- `display` allows you to change an `inline` element into a `block` element and vice versa.
- `display:inline` causes a block element to act like an inline element
- `display:block` causes an inline element to act like a block element
- `display:inline-block` causes a block element to flow like an inline element, while retaining other features of a block element.
- `display:none` hides and element from the page

## Hiding Boxes
- `visibility` allows you to hide boxes from users.
  - `hidden`
  - `visible`

## CSS3:
- Border Images
  - TODO read this section again
- Box Shadows
  - TODO read this section again
- Rounded Corners
  - TODO read this section again
- Elliptical Shapes 
  - TODO read this section again

## Switch Statements 162-182
- `switch` statements are used when there are many different outcomes to an evaluation.
```JavaScript
var msg;
var level = 1;
switch(level) {
  case 1:
    msg = "You are on the 1st level."
    break;
  case 2:
    msg = "You are on the 2nd level."
    break;
  case 3:
    msg = "You are on the 3rd level."
    break;
  default:
    msg = "You are on the 4th level."
    break;
}
```
## Type Coercion & Weak Typing
- If you use a data type JavaScript did not expect, it tries to make sense of the operation rather than report an error.
- JavaScript is a weakly typed language therefore type coercion can leand to unexpected values.
  - best to use `===` (strictly equal to) and `!==` vs <s>`==`</s> or <s>`!=`</s>.
- `NaN` is a value that is counted as a number. You'd see it if `'ten'/2`

### Truthy & Falsy Values
Due to type coercion every value in JS can be treated as if it were true or false.
- **Falsy** values are treated as if they are false

value | Description
--- | ---
`var x = false;` | Traditional Boolean false
`var x = 0;` | Number zero
`var x = '';` | NaN(Not a Number)
`var x = 10/'score;'` | Empty value
`var x;` | A var with no assigned value

- **Truthy** are treaded as if they are true

Value | Description
--- | ---
`var x = true;` | Boolean true
`var x = 1;` | Number other than zero
`var x = 'carrot';` | Not a blank string
`var x = 10/5;` | Number calculations
`var x = 'true';` | true written as a string
`var x = '0';` | Zero written as a string
`var x = 'false';` | False written as a string

## Checking Equality & Existence
Because the presence of an object or array can be considered truthy, it can be used to check for the existence of an element within a page.

- **Unary Operator** returns a result with just 1 operand.
  - `if(document.getElementById('head'))` would return `true`.

Expression | Result
--- | ---
`false == 0` | `true`
`false === 0` | `false`
`false == ''` | `true`
`false === ''` | `false`
`0 == ''` | `true`
`0 === ''` | `false`
`undefined == null` | `true`
`null == false` | `false`
`undefined == false` | `false`
`null == 0` | `false`
`undefined == 0` | `false`
`undefined === null` | `false`
`NaN == null` | `false`
`NaN == NaN` | `false`

## Short Circuit Values
- Logical operators are processed from left to right and can short-circuit as soon as they have a result.
- Loop keywords
  - `break` used to terminate the loop.
  - `continue` used to continue with the current iteration then check the condition again

## Loops
- sometimes you need to have the comp do something repeatedly
- 3 types of loops
    - for
        - When you know how many times you need to loop
    - while
        - when you don't know how many times you need to loop
    - do while
        - like a while loop but it will do the expression first before it starts looping.

### `For` Loops
- `for (var [counter] = [initialLoopValue]; [counter] < [stopping point]; [incrementor])

```javascript
for (var i = 0; i < 10; i++){
    [expression to be looped];
}
```

- Loop keywords
    - `break` will tell the program to stop looping.
    - `continue` will tell the program to continue looping

### `While` Loops
- a while loop uses to conditional statement to tell it what to do
    - `while(x === true) {[expression];}`
- a while loop will continue to do something along as the expression is true
- Usually you have to build your own counter inside the loop
    - while loops are more likely to be in a never ending loop.

```javascript
var x = 0;
while(x >= 10){
    console.log("I am number" + x + ".");
    x++;
}
```

- if `x` was already `>` than 10 then the loop won't even run.
- So sometimes you want to have it run at least once and thats whey you'd use a `do while` loop
```javascript
var x = 15;
do while(x>=0){
    console.log("Hello World!");
    x++;
}
```
- since x was already above 10 this code will only run once.