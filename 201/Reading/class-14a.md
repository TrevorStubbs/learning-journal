# Read 14a - CSS Transforms, Transitions, and Animations
- [Read this article on CSS Transforms](https://learn.shayhowe.com/advanced-html-css/css-transforms/)
- [Read this article on CSS Transitions & Animations](https://learn.shayhowe.com/advanced-html-css/transitions-animations/)
- [8 simple CSS3 transitions that will wow your users](https://www.webdesignerdepot.com/2014/05/8-simple-css3-transitions-that-will-wow-your-users/)
- [6 Buttons animated](https://codepen.io/retyui/pen/ByoaXV)
- [CSS3 Animations: Keyframes](https://codepen.io/akshaychauhan/pen/oAfae)
- [404](https://codepen.io/kieranfivestars/pen/MYdQxX)
- [Pure CSS Bounce Animation](https://codepen.io/dp_lewis/pen/gCfBv)



## CSS Transforms
- Transformation allows you to rotate, scale, move skew elements
- Syntax
```CSS
div{
  -webkit-transform: scale(1.5);
  -moz-transform: scale(1.5);
  -o-transform: scale(1.5);
  transform: scale(1.5);
}
```
### 2D Transformations
- `transform: rotate(20deg);` - will rotate the element from 0 to 360. Positive number: clockwise, Negative Number: anticlockwise.
- `transform: scale(.75)` - make the element smaller or bigger. 1 is the default. `> 1` for bigger `< 1` for smaller.
    - `scaleX` or `scaleY` or `scale(x, y)` will scale in a specific direction
### 2D Translate
- `translateX(-10px)` - moving the element without disrupting the document flow
- `translateY(25%)`
- `translate(-10px, 25%)`
### 2D Skew
- `skewX(5deg)`, `skewY(-20deg)` - to distort an element in a direction
### Can combine transformations
- `transform: rotate(20deg) scale(.75)`
### Transform Origin
### Perspective
### Perspective Depth Value
### 3D Transformations
- mostly the same just add a Z value. 
- Backface Visibility 

## Transitions & Animations
- use of pseudo-classes is an easy way to determine styles for different states.
- `transition-property`, `transition-duration`, `transition-timing-function`, and `transition-delay`
```CSS
.box {
  background: #2db34a;
  transition-property: background;
  transition-duration: 1s;
  transition-timing-function: linear;
}
.box:hover {
  background: #ff7b29;
}
```

- `transition-property` - determines exactly what properties will be altered
![properties](transitionalproperties.png)
- `transition-duration` - determines how long the transition will take
- `transition-timing-function` - determines the speed in which a transition will move.
- `transition-delay` - sets a delay
### Animations Keyframes

- `@keyframes` next to a selector will set the keyframes
```CSS
@keyframes slide {
  0% {
    left: 0;
    top: 0;
  }
  50% {
    left: 244px;
    top: 100px;
  }
  100% {
    left: 488px;
    top: 0;
  }
}
```
- Animation Name
    - Once the keyframes for an animation have been declared they need to be assigned to an element. 
```CSS
.stage:hover .ball {
  animation-name: slide;
}
```
- you can set animation duration, timing and delay like in a transformation
- `animation-duration`
- `animation-timing-function`
- `animation-delay`

- by default animations play only once
    - `animation-iteration-count: infinite;` will have the animation loop
- can alternate the animation direction with `animation-direction: alternate;`
- `animation-play-state: paused`
- `animation-fill-mode: forwards;`

## 8 Simple CSS Transitions
1. fade in
```CSS
.fade
{
    opacity:0.5;
}
.fade:hover
{
    opacity:1;
}
```

1. Change Color
```CSS
.color:hover
{
    background:#53a7ea;
}
```

1. Grow & Shrink
```CSS
.grow:hover
{
  -webkit-transform: scale(1.3);
  -ms-transform: scale(1.3);
  transform: scale(1.3);
}
.shrink:hover
{
  -webkit-transform: scale(0.8);
  -ms-transform: scale(0.8);
  transform: scale(0.8);
}
```
1. Rotate Elements
```CSS
.rotate:hover
{
  -webkit-transform: rotateZ(-30deg);
  -ms-transform: rotateZ(-30deg);
  transform: rotateZ(-30deg);
}
```
1. Square to circle
```CSS
.circle:hover
{
  border-radius:50%;
}
```
1. 3D Shadow
```CSS
.threed:hover
{
  box-shadow:
          1px 1px #53a7ea,
          2px 2px #53a7ea,
          3px 3px #53a7ea;
  -webkit-transform: translateX(-3px);
  transform: translateX(-3px);
}
```
1. Swing
```CSS
@-webkit-keyframes swing
{
  15%
  {
      -webkit-transform: translateX(5px);
      transform: translateX(5px);
  }
  30%
  {
      -webkit-transform: translateX(-5px);
      transform: translateX(-5px);
  } 
  50%
  {
      -webkit-transform: translateX(3px);
      transform: translateX(3px);
  }
  65%
  {
      -webkit-transform: translateX(-3px);
      transform: translateX(-3px);
  }
  80%
  {
      -webkit-transform: translateX(2px);
      transform: translateX(2px);
  }
  100%
  {
      -webkit-transform: translateX(0);
      transform: translateX(0);
  }
}
@keyframes swing
{
  15%
  {
      -webkit-transform: translateX(5px);
      transform: translateX(5px);
  }
  30%
  {
      -webkit-transform: translateX(-5px);
      transform: translateX(-5px);
  }
  50%
  {
      -webkit-transform: translateX(3px);
      transform: translateX(3px);
  }
  65%
  {
      -webkit-transform: translateX(-3px);
      transform: translateX(-3px);
  }
  80%
  {
      -webkit-transform: translateX(2px);
      transform: translateX(2px);
  }
  100%
  {
      -webkit-transform: translateX(0);
      transform: translateX(0);
  }
}
/*--- on the element ---*/
.swing:hover
{
  -webkit-animation: swing 1s ease;
  animation: swing 1s ease;
  -webkit-animation-iteration-count: 1;
  animation-iteration-count: 1;
}
```
1. Insert Border
```CSS
.border:hover
{
  box-shadow: inset 0 0 0 25px #53a7ea;
}
```
