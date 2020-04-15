# Read: 05 - Design web pages with CSS
#### 4/15/20

## Intro To CSS
### Everything is a box
- Each element in HTML is a [box](http://www.htmlandcssbook.com/code-samples/chapter-10/thinking-inside-the-box.html) that CSS can individually style.
    - Example Styles:
        - Boxes: Width and height, Boarders (color, width and style) background color and images position in the browser window.
        - Text: Typeface, size, color, italics, bold uppercase, lowercase,  small-caps
        
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

### CSS Color
#### Ways to specify a color
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

### Foreground vs Background
- Foreground
    - `color: [value];`
- Background
    - `background-color: [value];`

### Basic Explantion of Computer Color
- RGB Values
- Hex Codes
- Color Names
- Hue
    - Colloquial idea of specific color 
- Saturation
    - The amount of gray in a color
- Brightness
    - how much black in a color

#### Contrast
- Low Contrast
    - Text is harder to read on a low contras background
- High Contrast
    - Easier to read but can cause eye strain of a long time
- Medium
    - Good if your asking your reader to spend a good amount of time reading your site.

#### Opacity
- How much you can see through a color.
    - A value between 0.0-1.0
    - `opacity: [number];`
    ```CSS
    p.one {
        background-color: rgb(0,0,0);
        opacity: 0.5;}
    ```

### HSL Color (Hue, Saturation, Lightness)
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
