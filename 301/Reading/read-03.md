# Read: 03 - Flexbox and Templating
#### 5/29/20

- [Templating with Mustache](https://medium.com/@1sherlynn/javascript-templating-language-and-engine-mustache-js-with-node-and-express-f4c2530e73b2)
- [A Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox Froggy](https://flexboxfroggy.com/)
- Reference: [Mustache.js Official Documentation](https://github.com/janl/mustache.js)

## JavaScript Templating Language and Engine
### JavaScript Templating
- The template is HTML markup, with added templating tags.
    - The template engin replaces variables and instance declarations in a template file.
### Mustache
- Works by expanding tags in a template using values provided in a shah or object.
    - referred as 'logic-less'
        - no if, else or lops. Replaced all with tags.
``` JavaScript
Mustache.render(“Hello, {{name}}”, { name: “Sherlynn” });
// returns: Hello, Sherlynn
```
- the 2 braces '{{}}' show that this is a placeholder
- Mustache is a specification for a templating language but not a templating language itself.
### Mustache-Express
- mustache for node and express.
> `npm install mustache --save`
- Configure mustache-express
``` JavaScript
var mustachExpress = require('mustache-express');
// Register '.mustache' extension with The Mustache Express
app.engine('html', mustacheExpress());

app.set('view engine', 'html');
app.set('view', _dirname + '/src/views');
```

## Complete Guide to Flexbox
- 'Flexbox Layout' is a module aimed at providing an efficent way to lay out, align and distribute space among items in a container. 
- A flex container expands items to fill availble free space or shirnks them to prevent overflow.
- Flex layout is based on flex-flow direcions. 
### Terms
- main axis – The main axis of a flex container is the primary axis along which flex items are laid out. Beware, it is not necessarily horizontal; it depends on the flex-direction property (see below).
- main-start | main-end – The flex items are placed within the container starting from main-start and going to main-end.
- main size – A flex item’s width or height, whichever is in the main dimension, is the item’s main size. The flex item’s main size property is either the ‘width’ or ‘height’ property, whichever is in the main dimension.
- cross axis – The axis perpendicular to the main axis is called the cross axis. Its direction depends on the main axis direction.
- cross-start | cross-end – Flex lines are filled with items and placed into the container starting on the cross-start side of the flex container and going toward the cross-end side.
- cross size – The width or height of a flex item, whichever is in the cross dimension, is the item’s cross size. The cross size property is whichever of ‘width’ or ‘height’ that is in the cross dimension.
### Properties for parent
- display
    - flex or inline-flex
``` CSS
.container{
    display: flex; /* or inline-flex */
}
```
- flex-direction
    - row (default) - left to right `ltr`; right to left `rtl`
    - row-reverse
    - column: same as row but top to bottom
    - column-reverse: bottom to top.
- flex-wrap
    - nowrap (default) - all flex items will be on 1 line
    - wrap - flex items will wrap onto multiple lines, from top to bottom.
    - wrap-reverse - items will wrap onto multpuple lines from bottom to top. 
- flex-flow - shorthand for flex-direction and flex-wrap
    - row nowrap (default)
- justify-content
    - flex-start (defalt)
    - flex-end
    - start
    - end
    - left
    - right
    - center
    - space-between
    - space-around
    - space-evenly
- align-items
    - stretch
    - flex-start / start / self-start
    - flex-end / end / self-end
    - center
    - baseline
- align-content
    - flex-start/ start
    - flex-end / end
    - center
    - space-between
    - space-around
    - space-evenly
    - stretch
### Properties for Children
- order - any integer value
- flex-grow
- flex-shrink
- flex-basis
- flex
- align-self
