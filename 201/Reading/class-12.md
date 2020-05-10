# Class 11 - Read: 12 - Docs for the HTML <canvas> Element & Chart.js
#### 5/9/20
- Charts API
- [Introduction](https://www.chartjs.org/docs/latest/)
- [Basic Usage](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage)
- [Drawing shapes with canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes)
- [Applying styles and color](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors)
- [Drawing text](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)

## Introduction
- use `<canvas>` to render the chart
- need to define it's width and height using HTML
## Basic Usage
- `<canvas>` is like an img without the alt or title
    - the width and height can be ommited and use the DOM to control those attributes.
- good idea to give the canvas and `id`
### Fallback content
- it is easy (and a good idea) to give canvas a 'fallback'.
    - just insert the fallback content inside the `<canvas>` tag
```HTML
<canvas id="clock" with="150" height="150">
  <img src="images/clock.png" width="150" height="150" alt=""/>
</canvas>
```
- canvas requres a closing tag
### Rendering
- canvas can render 2D graphics but can also render 3D using WebGL inside the OpenGL ES.
### Drawing shapes
- Coordinate (0,0) is the top left hand corner.
### Drawing Rectangles
- `fillRect(x,y,width,height)` - filled in rectangle
- `strokeRect()` - rectangle outline
- `clearRect()` clears the rectangle making it transparent

### Draw Paths
1. create the path
1. use drawing commands to fill the path
1. once created uses stroke or fill to render it
- `beginPath()` - Creates a path
- `closePath()` - adds a straight lin to the path
- `stroke()` and `fill()`
### Drawing rectangles
```JavaScript
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.beginPath(); // begin
    ctx.moveTo(75, 50); // move pen to here
    ctx.lineTo(100, 75); //draw a line to here
    ctx.lineTo(100, 25); // draw aline to here
    ctx.fill(); // fill in the area
  }
}
```

### Moving the Pen
- `moveTo(x,y)` doesn't draw anything but moves the 'pen' to the coordinates
### Lines
- `lineTo(x,y)` draws a line from curren pen position to the coordinates
### Arcs
- `arc(x,y,radius,startAngle,endAngle, anticlockwise)`
- `arcTo(x1,y1, x2,y2 radius)`
### Path2D objects

## Applying Styles and Colors
### Colors
- `fillStyle = color` - color name or RGB
- `strokeStyle = color`
### Transparency
- add a 4th value to the RGB to get the transparency value (rgba())
### Line styles
- `lineWidth = value`
- `lineCap = type`
- `lineJoin = type`
- `miterLimit = value`
- `getLineDash()` - gets the pattern
- `setLineDash(segments)` - sets the pattern
- `lineDashOffset = value` - where to start the dash array
### Gradients
 - `createLinearGradient(x1,y1, x2, y2)`
 - `createRadialGradient(x1, y1, r1, x2, y2, r2)`
### Patterns
- `createPattern(image, type)` 
    - repeat
    - repeat-x
    - repeat-y
    - no-repeat
### Shadows
- `shadowOffsetX = float`
- `shadowOffsetY = float`
- `shadowBlur = float`
- `shadowColor = color`
## Drawing Text
- `fillText(text, x, y, [, maxWidth])`
- `strokeText(text, x, y, [, maxWidth])`
### Styling Text
- `font = value`
- `textAlign = value`
- `textBaseline = value`
- `direction = value`

