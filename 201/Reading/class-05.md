# Read: 05 - HTML Images; CSS Color & Text
#### 4/29/20

## Images
- How to include an image
- Which format to use
- How to size
- Optimize

### Choosing Images
- They can set the tone.
- A picture is worth 1000 words
- Images should:
  - Be relevant
  - Convey information
  - Convey the right mood
  - Be instantly recognizable
  - Fit the color palette
- You must either own the image or own the right to the image
- Make sure your images are organized

### Adding Images
- `<img src="[image location]" alt="[Description of the image if it doesn't load]" title="[description for the tooltip]" />`  It's a self closing tab

### Height & Width (old)
- `height` and `width` properties can be used within the element tag (defined with pixels).
  - Setting the image this way can cause the image to load slower
  - This is not current industry standard

### Where to place
1. Before a `<p>`
    - Paragraph starts a new line after the img
1. At the start of a `<p>`
    - First row of text aligns with the bottom of the image
1. In the middle of a `<p>`
    - Image is placed between the word of the paragraph

### Aligning Images (Old)
- `align="[left]|[right]"` Aligns the the image horizontally to the left or right 
- `align="[top]|[middle]|[bottom]"` The first line to the top of the image|First line in the middle of the image| first line to the bottom of the image

### Rules for Images
1. Save Images in the correct format
    - jpeg - good for photos
    - gif - limited color pallet good for short skits
    - png - good for vector graphics
      - good for transparent images

1. Save images in the correct size
    - Save the image at the same w/h it will appear on the website

1. Use the correct resolution
    - Most monitors are at 72ppi.
    - Don't save images higher than that or they will take longer to load.

### Image Tools
- Adobe Photoshop
- Pixelmator
- PaintShopPro
- GIMP

### Transparency
- Straight
- diagonal
- round
- semi-opaque
- drop-shadow

### Figure and Caption
- `<figure>` and `<caption>` figure is a container element and figcaption allows for a caption to be added to an image.

## Color
### Ways to specify a color
- RGB Values (values from 0, 255)
    - `color: rgb(r ,g ,b )`
    ```CSS
    p {
        color: rgb(100,100,90);}
    ```
- Hex Code 
    - `color: #[specific color's hex code]`
    ```CSS
    p{
        color: #ee3e80;}
    ```
- Color names
    - `color: [ColorName]`
    ```CSS
    p{
        color: DarkCyan;}
    ```

## Foreground vs Background
- Foreground
    - `color: [value];`
- Background
    - `background-color: [value];`

## Basic Explanation of Computer Color
- RGB Values
- Hex Codes
- Color Names
- Hue
    - Colloquial idea of specific color 
- Saturation
    - The amount of gray in a color
- Brightness
    - how much black in a color

### Contrast
- Low Contrast
    - Text is harder to read on a low contras background
- High Contrast
    - Easier to read but can cause eye strain of a long time
- Medium
    - Good if your asking your reader to spend a good amount of time reading your site.

### Opacity
- How much you can see through a color.
    - A value between 0.0-1.0
    - `opacity: [number];`
    ```CSS
    p.one {
        background-color: rgb(0,0,0);
        opacity: 0.5;}
    ```

## HSL Color (Hue, Saturation, Lightness)
- Hue as angle between 0 - 360
- Saturation as a percentage between 0% - 100%
- Lightness (Brightness) as a percentage between 100%(whiteout) - 50% (normal) - 100% (black)
- `hsl([number], [number]%, [number]%)`
```CSS
body{
    background-color: #C8C8C8;
    background-color: hsl(0, 0%, 78%);}
```
- There is also hsla. The a = alpha
- a = opacity. 
    - Pressed as a number between 0.0-1.0
- `hsl([number], [number]%, [number]%, [number])`
```CSS
body{
    background-color: #C8C8C8;
    background-color: hsla(0, 0%, 78%, 0.5);}
```

## Text 264-299
- 2 properties that control the appearance of text
    - Those that directly affec the font and its appearance
- Those that would have the same effect on text no matter what font you were using.

### Typeface Terms
- Serif
    - little feet
- Sans-serif
    - no little feet
- monospaced
    - each letter take the same width
    - looks like a typewriter
- weight - (bold)
    - affects the amount of white space and contrast on a page
    - can add emphasis
- style - (italic)
- stretch

### Choosing a typeface
- A browser will only display a font that it has
    - serif
      - the eye flows from letter to letter
    - san-serif
      - looks cleaner

### Most Browsers have these fonts
- Monospace
- Cursive
- Fantasy

### Getting more fonts
- Typefaces can be © so be respective of their licenses.

### Specifying Typefaces
- `font-family` allows you to specify the type face that should be used..
- can separate fonts by a comma so that if the browser doesn't have 1 it can load the next one.
- `font-size` pg. 276 for sizing chart
    - pixels: allows for precision
    - percentages: default browser size is 16px.  
        - great for dynamic websites
    - em: equivalent ot the width 'm'. (as defined by the typeface docs)
- `@font-face` allows you to specify a path to a copy of the font which will be downloaded if it's not on the user's machine. (careful of ©)
```CSS
@font-face {
  font-family: 'ChunkFiveRegular';
  src: url('fonts/chunkfive.eot');
}
```

### Font Formats
- use this order for your fonts
    1. eot
    1. woff
    1. ttf/otf
    1. svg

### font-weight
- `normal` default
- `bold` modern proper way of making text bold

### font-style
- `normal` default
- `italic`
- `oblique` 

### Uppercase & Lowercase
- `text-transform: uppercase` - makes all the text uppercase
- `lowercase` - make text lowercase
- `capitalize` - causes the first letter of each work to appear capitalized.

### Underline & Strike
- `text-decoration: underline` underlines text
- `overline` a line on top of text
- `line-through` strikes out the text
- `blink` makes the text flash on and off
- `none` removes any of the above

### Leading
- `line-height: 2em` like double-spacing in a word processor. Uses `em`s.

### Letter & Word Spacing
- `letter-spacing: 0.2em` - space between each letter. Uses `em`
- `word-spacing: 1em` - space between each word. Uses `em`

### Alignment
- `text-align` 
    - `left right center justify`

### Vertical
- `vertical-align` 
    - `baseline sub super top text-top middle bottom text-bottom`

### Indenting Text
- `text-indent`- indentation, uses pixels.

### Drop shadow
- `text-shadow`
    - 3 lengths and a color.
    - length 1 - left and right
    - length 2 - top and bottom
    - length 3 - amount of blur

### First Letter or Line - pseudo
- Child selector (`p.intro:first-letter`)
- `first-letter` style in this selector apply to first letter 
- `first-line` style in this selector apply to first line in this element

### Styling Link - pseudo
- `:link` set a style to a link that has NOT been visited
- `:visited` set a style to a link that HAS been visited.

### Responding to Users
- `:hover` applies style when the mouse is over the element
- `:active` style applied when an element is being activated by a user. (usually clicked)
- `:focus`  style applied when the element has focus. 

### Attribute Selectors pg 292