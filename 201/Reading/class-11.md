# Read: 11 - Assorted Topics
- Images pg 406-427
- Practical Information pg 476-492
- [MDN on audio and video](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)
- Flash pg 201-206 (skim)

## Images 406-427
### Controlling the Size of images in CSS
- `width: px;`
- `height: px;`
    - choose 1 or the other. Don't change both.
### Aligning Images
- Use float
    - `float: left;`
### Centering Images with CSS
- by default images are inline elements
1. make the image a block-level element
1. On the conatianing element you can use `text-align:center`
1. Or on the image itself, you can use the margin property and set the values of the left and right to auto.
```CSS
img.align-center{
  display:block;
  margin: 0px auto;
  }
```
### Background Images
`background-image: url("path/image.gif")`
### Repeating Images
- `background-repeat`
    - `repeat` - background image is repeated vertically and horizontally
    - `repeat-x` - repeats horizontally
    - `repeat-y` - repeats vertically
    - `no-repeat` - image is only shown once
    - `fixed` - image stays in the same postion
    - `scroll` - image moves up and down as the user scrolls
### Positioning
- `background-position:`
    - `left top`
    - `left center`
    - `left bottom`
    - `center top` 
    - `center center`
    - `center bottom`
    - `right top`
    - `right center`
    - `right bottom`
### Shorthand
1. color
1. image (url)
1. repeat
1. attachment
1. position
### Image Rollover & Sprite
Set up 3 settings for the same image
1. for no mouse over
1. for hover
1. for active
### CSS Gradient
1. use webkit gradient add a gradient to a background image
### Contrast of Background Images
## Practical Information pg 476-492