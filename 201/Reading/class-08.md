# Read: 09 - Forms and Events
#### 5/3/20

- forms pg 144-175
- lists pg 330-357
- events pg 243-292

## Forms 144-175
- Ways for users to communicate with your website

### Form Controls
- Adding Text
    - Text input (single-line)
    - Password input
    - Text area (multi-line)
- Making Choices:
    - Radio buttons
    - Checkboxes
    - Drop-down boxes
- Submitting forms:
    - Submit buttons
    - Image buttons
- Uploading Files:
    - File upload
### Form Structure
> `<form action="[URL]" method="get">`
- `<form>` - Form controls live inside this element.
- `action` - (Required) Its value is the URL for the page on the server that will receive the info.
- `method` - Forms can be sent using either 'get' or 'post'
    - `get` - the values from the form are added to the end of the URL. Are good for:
        - short forms
        - when you are just retrieving data from the web server (not sending info that should be added to or deleted from a database)
    - `post` - values are sent in HTTP headers. good for:
        - allows users to upload a file
        - is very long
        - contains sensitive data (passwords)
        - adds info to or deletes info from a database.
- `id` - this is the element ID
### Text input
> `<input type="text" name="username" size="15" maxlength="30>`
- `<input>` - tells the browser that this is an input
- `type="text"` - creates a single-line text input.
- `name` - How to label and control the info
- `size` - (Old) How many characters can be displayed
- `maxlength` - Used to define how many chars can be placed in the text box
### Password input
> `<input type="password" name="password" size="15" maxlength="30">`
- `<input>` - tells the browser that this is an input
- `type="password"` - creates a single-line input but the data entered are starred out.
- `name` - same as above
- `size`, `maxlength` - same as above
### Text area
> `<textarea name="comments" cols="20" rows="4"/>` 
- `<textarea>` creates a multi-line input form
- `cols`, `rows` - (Old) Indicatees how many colomns/rows should take up.
### Radio Buttons
> `<input type="radio" name="genre" value="rock">`
- `<input>` - tells the browser that this is an input
- `type="radio"` - creates a radio button on the page
- `name` - same as above
-  `value` - indicate4s the value that is sent to the server for the selected button.
- `checked` - this one will be checked when the page loads.
### Checkbox
> `<input type="checkbox" name="service" value="itunes" checked="checked" />`
- `<input>` - tells the browser that this is an input
- `type="checkbox"` - creates a checkbox on the page
- `name` - same
- `value` - same
- `checked` - this checkbox will be checked when the page loads.
### Drop Down List
```HTML
<select name="devices">
  <option value="ipod">ipod</option>
```
- `<select>` - creates a selection box (drop-down box)
- `name` - same
- `<option>` - specifies the options that the user can select from
- `value` - same
- `selected` - this one will be selected when the page loads
### Multipul Select Box
```HTML
<select name="instruments" size="3" multiple="multiple">
  <option value="guitar" selected="selected">Guitar</option>
```
- `<select>` - same as above
- `<multiple>` - tells the browser that this box is a multi-select box
### File Input Boc
> `<input type="file" name="user-song" />`
- `<input>` - Creates an input box
- `type="file"` - This creates a box that looks like a text input box followed by a browse button.
### Submit Button
> `<input type="submit" name="subscribe" value="Subscribe" />`
- `<input>` - same
- `type="submit"` - Tells the browser to make a submit button
- `name` - what is used by the server
- `value` - is what is displayed
### Image Button
> `<input type="image" src="images/subscribe.jpg" width="100" height="20" />`
- Combines the submit button with an image into 1 tag. 
### Button & Hidden Controls
> `<button><img src="[directoryPath]" alt="add" />`
- Allows you to combine text and images in between button tags to give them button functionality.
- `<input type="hidden">` - Allows the web page to add values to forms that users cannot see.
### Labelling Form Controls
- `<label>` - Allows for accessibility for vision-impaired users.
> `<label for="female">Female</label>`
- `for` - tells the browser what the button is for.
### Grouping Form Elements
- You can group related form controls together inside the `<fieldset>` element.
    - `<legend>` - The label of the grouped elements
### HTML5 Inputs
- Form Validation - Gives a message to the user if the form isn't filled in correctly
- `required="required"`
- Date Input
    > `<input type="date">` 
- Email & URL
    - `type="email"`, `type="URL"`
- Search Input
    - `type="search"`
    - `placeholder`

## CSS Lists pg 330-357
### Bullet Point Styles
```CSS
ol{
  list-style-type: disc;
}
```
- `list-style-type` - Allows you to control the shape and stile of a list marker.
- `<ul>` 
    - none, disc, circle, square
- `<ol>`
    - decimal, decimal-leading-zero, lower-alpha, upper-alpha, lower-roman, upper-roman
- `list-style-image` - to use an image for a bullet point
```CSS
ul{
  list-style-image: url("[imgURL]");
}
```
- `list-style-position` - `inside` or `outside` will position the bullets/numbers inside or outside of the containing box. 
 -`list-style` - shorthand for the upper styles

### Table Properties
- `width` - sets the width of the table
- `padding` - sets the padding between the text/info and the border
- `text-transform` - converts the content of the table headers to uppercase
- `letter-spacing`, `font-size` - sets the space between the letters. Sets the text font size
- `border-top`, `border-bottom` - set borders above and below the table headers
- `text-align` align the text to the left of some table cells and to the right of the others
- `background-color`
- `:hover` highlight a table row when a user mouses over it.
#### Empty cells
`empty-cells` - allows for attributes to be assigned to empty cells
- `show` shows the borders of any empty cells
- `hide` hides the border
- `inherit` if you have one table nested inside another, the inherit value instructs the table cells to obey the rules of the containing table. 
#### Gaps between cells
- `border-spacing` - distance between cells
- `border-collapse` 
    - `collapse` - borders collapse into a single border when possible
    - `separate` - borders detached from each other
### Styling forms
- Common styling
    - text input and text areas
    - submit buttons
    - labels on forms to get the form controls to align nicely
### Styling Text inputs
- `border-radius` round the corners.
### Styling Submit buttons
- `text-shadow` can give a 3D look to the text.
- `bottom-border` gives a 3D effect
- `:hover` make the button responsive to the user
### Styling Fieldsets & Legends
- Field sets can help group items together in a long form.
### Aligning Form Controls pg 345-346
### Cursor Styles
```CSS
a{
  cursor: move;
}
```
- `auto`
- `crosshair`
- `default`
- `pointer`
- `move`
- `text`
- `wait`
- `help`
- `url("[gifURL]")`

## Events pg 243-292