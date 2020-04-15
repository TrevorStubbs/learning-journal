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
Descendant Selector | 


