# Read: 01 - SMACSS and Responsive Web Design
#### 5/28/20
[Shay Howe's intro to RWD](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/)
[All About Floats](https://css-tricks.com/all-about-floats/)
[Don't Overthink Grids](https://css-tricks.com/dont-overthink-it-grids/)
[CSS Floats Explained](https://www.freecodecamp.org/news/css-floats-explained-by-riding-an-escalator-57fa55232333/)
[SMACSS](http://smacss.com/)


## Responsive Web Design
- How to build websites suitable for all users?
### Overview
- Responsive Web Design (RWD) is the practice of building a website suitable to work on every device and every screen size.
### Responsive vs. Adaptive vs Mobile
- Responsive
    - To react quickly and positively to any change
- Adaptive
    - To be easily modified for a new purpose or situation.
- Mobile
    - To build a separate website commonly on a new domain solely for mobile users.
### Flexible Layouts
-  The practice of building the layout of a website with a flexible grid, capable of dynamically resizing to any width. 
    - us of percentages or `em` units. 
- CSS relative length units
    - `vw` - viewport width
    - `vh` - viewport height
    - `vmin` - Minimum of the viewport's height and width
    - `vmax` - Maximum of the viewport's height and width
### Flexible Grid
- use percentages
### Media Queries - not supported below IE8
- Provide the ability to specify different styles for individual browser and device circumstances. 
- Initializing Media Queries
    - `@media`
        - `all`, `screen`, `print`, `tv`, `braille`
- Logical Operators in Media Queries
    - `and`, `not`, `only`
- min - greater than or equal to
- max - less than or equal to
- Height & Width
    - `@media all and (min-width: 320px) and (max-width: 780px){...}`
- orientation:
    - `@media all and (orientation: landscape) {...}`
- aspect ratio
    - `@media all and (min-device-aspect-ratio: 16/9) {...}`
- Resolution:
    - `@media print and (min-resolution:300dpi) {...}`
- Media Queries Demo
``` CSS
@media and (max-width:420px){
    section, aside{
        float: none;
        width: auto;
    }
}
```
### Mobile First Design
- Design for a small screen first.
    - Avoid shadows, gradients, transforms and animation on mobile styles. 
### Viewport
> name="viewport content=""
- Height & Width
    - `<meta name="viewport" content="width=device-width">`
- Scale
    - `minimum-scale`, `maximum-scale`, `initial-scale`, `user-scalable`(bool)
        - inteter between 0 - 10
- Resolution
    - target-densitydpi=
        - device-dpi, high-dpi, medium-dpi, low-dpi, [actualNumber]
### Flexible Media

---
 
## Floats
- Float is a CSS positioning property.
- `float: left;`
- `clear: both;`
### The great Collapse
- If a parent element contains nothing bug floated elements, the height of it will collapse to nothing. 
    - Fix: clearing the float after the floated elements in the container but before the close of the container. 
        - The Empty Div Method: `<div style="clear: both;"></div>`
        - The Overflow Method: set the overflow property on a parent element.
            - If this is set to auto or hidden on the parent element, the parent will expand to contain the floats. 
        - The Easy Clearing Method: `:after`
        ``` CSS
        .clearfix:after { 
            content: "."; 
            visibility: hidden; 
            display: block; 
            height: 0; 
            clear: both;
        }
        ```
### Problems with Floats
- Pushdown: A symptom of an element inside a floated item being wider than the float itself. 
    - Fix: `overflow: hidden`
- Double Margin Bug: if you apply a margin in the same direction as the float, it will double the margin
    - Fix: `display:inline`
- 3px Job: When text that is up next to a floated element is mysteriously kicked away by 3px.
    - Fix: set a width or height on the effected text.
- Bottom Margin Bug: when a floated parent has floated children inside it, bottom margin on those children is ignored by the parent.
    - Fix: using bottom padding on the parent instead.

## Don't Over Think Grids
- Context
    - A block level element is as wide as the parent it's inside.
- Columns
```HTML
<div class="grid">
  <div class="col-2-3">
     Main Content
  </div>
  <div class="col-1-3">
     Sidebar
  </div>
</div>
```

``` CSS
[class*='col-'] {
  float: left;
}

.col-2-3 {
  width: 66.66%;
}
.col-1-3 {
  width: 33.33%;
}
```
> This will cause the parent element to collapse to zero. Fix:

``` CSS
.grid:after {
  content: "";
  display: table;
  clear: both;
}
```
- Gutters
    - use `box-sizing: border-box;`

```CSS 
*, *:after, *:before {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
```
    - Now set a width

```CSS
[class*='col-'] {
  padding-right: 20px;
}
[class*='col-']:last-of-type {
  padding-right: 0;
}
```

## CSS Floats Explained By Riding An Escalator
- Floats create alternate flows
- FLoats allow you to create new relationships between flows. 
- “Clear: left” tells each person floating left that they should align themselves behind the first element that is floated left. 

## SMACSS
> Scalable and Modular Architecture for CSS
1. base
    - defaults: single element selectors
1. layout
    - divied the page into sections. Layouts hold 1 or more modules together
1. module
    - The Reusable, modular parts of the design.
    - Callouts, sidebar sections and product lists
    - Avoid element selectors
1. state
    - Rule that describe how the modules and/or layouts will look when in a particular state. 
    - Hidden/expanded or active/inactive
1. theme

### Naming Rules:
- `l-` or `layout-`
- `is-` for state