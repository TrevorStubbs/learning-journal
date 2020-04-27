# Read: 01 - Introductory HTML and JavaScript
#### 4/24/20

## Intro
- Like any coding HTML/CSS looks complicated but it's actually just a series of small easy steps.
1. HTML: What is on the page
1. CSS: How the page looks

## How people access the web
- People interact with the web through a web browser
    - the browser it the pice of software that translates HTML/CSS/JavaScript into the web pages people use. 
- Web Server
    - The web server is the location where the webpages are stored and accessed.
- Devices
    - Web pages can be found on many different devices. they all have browsers but they can present the pages in very different ways.

## How are site created
- What you see
    - What a user see is the translated HTML and CSS.
- A web site is a collection of web pages arranged (hopefully) in a understandable way.

## How does the web work
- Each website had an address (IP Address)
    - But us humans have a hard time remembering numbers so there is a DNS (Domain Name System) that connects webpage names with their IP Address.
- When a user goes to a website their computer sends out a request along with their own IP address. That way the web knows what to look for and who to send the data back to.


## Structure
- A webpage is structured very closely to a normal word processor document.
    - the difference is you can't send plain text
    - You have to surround the text with tags so the browser knows what and where to place them on a page.
- The main part of the page lives between the `<body>` tags.
- You can make headers by using the `<h1></h1>`.
    - headers can go all the way down to `<h6>`

```html
<html>
    <head>
        <title>What it shows up on the tab</title>        
    </head>
    <body>
    <h1></h1>
    </body>
</html>
```
- The code in blue are called elements.
- elements are surrounded by tags `<>`
- many elements have the ability to take in attributes
```html
<p lang="en-us">lang is the attribute name and "en-us" is the attribute value.</p>
```
- the `<head>` element contains info about the page.

## Extra Markup
### HTML4
- 1997
### XHTML 1.0
- 2000
- It's HTML4 reformulated to follow XML rules. Those rules include:
    - Every element needed a closing tag
    - Attribute names had to be lowercase
    - All attributes required a value, and all values are to be in double quotes `""`.
    - Deprecated elements should no longer be used.
    - Every element that was opened inside another element should be closed inside that same element.

- There was 2 flavors of XHTML 1.0
    - Strict XHTML 1.0
        - Rules are followed to the letter
    - Transitional XHTMl 1.0
        - users could still use presentational elements.

### HTML5
- 2000
- Not strict like XHTML
- Closing tags are not required. 

### Telling the browser what you are doing.
- Use a `<!DOCTYPE html>`
    - the DOCTYPE tells the browser what kind of document it is.

### Comments
- Comment example in HTML
```HTML
<!-- This is my comment -->
```

### ID Attribute
- use the `id="[name"]` attribute to name an element
    - this is case sensitive

### Class Attribute
- use the `class="[name]"` attribute if you want to select multiple elements.

### Block Elements
- Elements that always appear to start on a new line are called `block level elements`.
    - `<h>`, `<p>`, `<ul>`, and `<li>`

### Inline Elements
- Elements that always appear to continue on the same line are called inline elements
    - `<a>`, `<b>`, `<em>`, and `<img>`

### Grouping text & Elements in a block
- The `<div>` element will group everything between its tags into a separate block.
    - It can also make it easier to follow your code if you have used `<div>` elements to hold each section of the page.

### Grouping text & and elements inline
- The `<span>` element is the inline equivalent of the `<div>`.
    - It's commonly used to make and ID or a class on a piece of text without breaking it up.

### IFrames
- `<iframe>` element is like a little window that has been cut into your page.
    - A little window into another website.
    - has these attributes:
        - src - the URL of the page to be shown in the window
        - height- the window's height
        - width - the window's width
        - scrolling - (not HTML5 Supported) allows for scrolling around that iframed website
        - frameborder - (not HTML5 supported) If the frame has a border or not
        - seamless - no border or scrolling

### Info about the pages
- `<meta>` element lives inside the `<head>` and it contains info about the web page.
    - not seen by the user
    - can tell search engines about the page
    - `<meta>` is an empty element (no closing tag)
        - all the data is in its attributes
    - most common attributes is the name and content attributes
    - `description`: contains a description of the page.
        - So search engines can understand what the page is about (max 155 characters.)
    - `keywords`: a list of comma separated words that a user might search for.
    - `robots`: indicates whether search engines should add this page to their search results.
    - `author`
    - `pragma`: prevent the browser from caching the page.
    - `expires`: tells the browser when the page should expire (no longer cached).

```HTML
<!DOCTYPE html>
<html>
    <head>
        <title>Information About Your Pages</title>
        <meta name="description"
        content="An Essay on Installation Art" />
        <meta name="keywords"
        content="installation, art, opinion" />
        <meta name="robots"
        content="nofollow" />
        <meta http-equiv="author"
        content="Jon Duckett" />
        meta http-equiv="pragma"
        content="no-cache" />
        <meta http-equiv="expires"
        content="Fri, 04 Apr 2014 23:59:59 GMT" />
    </head>
    <body>
    </body>
</html>
```

### Escape Characters
- TODO look up how to use these characters

## HTML5 Layout
- HTML5 introduces more tags to go along with the `<div>` tags
- Some of the new tags include

```HTML
<header>
<nav>
<article>
<aside>
<footer>
<section>
<hgroup>
<figure>
```

- `<header>` is used to contain the site name and navigation functions
- `<footer>` is for copyright info along with privacy policies and terms and conditions.
- `<nav>` contains the major navigation blocks
- `<article>` is a container for any section of a page that could stand alone.
    - can be nested inside one another
- `<aside>` can be used inside a `<article>` or outside
    - Inside: contains info that is related but not essential to the overall meaning
    - Outside: ats as a container for content that is related to the entire page
- `<section>` groups related content together and typically would have its own heading.
- `<hgroup>` used to group together a set of `<h>` elements so they can treated as 1 single heading.
- `<figure>` goes with `<figcaption>` and is used to contain any content that is referenced from the main flow of an article. (not images)
- `<div>` is still used but used to group related elements together.

### Older Browsers
They won't know how to render these new elements properly. Use this CSS and html:

```CSS
header, section, footer, aside, nav, article, figure
{
    display: block;}
```

```HTML
<!--[if lt ID 9]>
    <script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
<![endif]-->
```

## Process & Design

## Who is this site for?
### Are your readers Individuals?
- Whats the age range
- What region is the site for
- Do your readers live in the country or the city
- What's their education level
- Is your site occupation specific

### Is your target audience a company?
- What is the size of the company
- Are you targeting a specific department?
- Will the reader be visiting the site for someone else?
- What is your target's budget

## Why are people visiting your website?
- What is their motivation to be here
- What is their goal? What do they want to get out of your site?

### Key Motivations
- Are they here for entertainment?
- Is their goal professional or personal?
- Is there time here essential or a luxury?

### Specific Goals
- Do they want general or specific information? 
- How familiar are they with the subject matter?
- Are they looking for time sensitive info?
- Do they need to contact you?

## What info do they need?
- Does your audience need to be introduced to what your showing?
- Do they need background info?
- What are the most important features of what you are offering.
- What are common questions people have about what you are showing.

## How often are people going to be visiting your site?
- It will determine how often you have to update your site

## Create a [site map](https://en.wikipedia.org/wiki/Site_map)
- Create a diagram of the pages that will be used to structure the site. 
- Create a [card sorting](https://www.usability.gov/how-to-and-tools/methods/card-sorting.html) system.
    - card sorting helps visualize the structure of your site
    - card sorting allows for customers to help guide the design process
- Start with the homepage and try to think what would be the most logical next step.

![site map example](https://landing.moqups.com/img/content/diagrams/site-maps/ecommerce-shop-sitemap-template.png)

---

## Create a [Wireframe](https://en.wikipedia.org/wiki/Website_wireframe)
- A wireframe is a basic outline of a web page
- It's a basic sketch of the key information and layout that needs to go on a page.
- It help guide the construction of the site
- Don't include colors, fonts, backgrounds or images.
- Focus on what information needs to be on each page.
![wireframe example](https://file.mockplus.com/image/2019/07/6a31adb2-6ce4-41d8-b6a9-b543f76cf92f.png)

---

## Communicate your message through your design
- Organize and prioritize the information
- Distinct look draws attention 
    - use it focus the eye on the most important parts of your page
- Group related content into chunks
    - makes it easier for your audience to find the info they want/need

## Visual Hierarchy
- Most readers don't read an entire page.
- Guide the reader by making a visual hierarchy.
    - Size: Large elements draw the eye
    - Color: Brighter sections draws the user's attention
    - Style: A change of *style* will trigger the brain to look.

## Grouping
- Pay attention to the grouping of information
    - Proximity: Items closed together seems related to each other.
    - Closure: Complicated arrangements cause the brain to look for a pattern.
    - Continuance: A line or a curve will guide the reader to the next part.
    - White Space: Indicate that items are not related.
    - Color: Color background will emphasize a connection
    - Boarders: help with grouping ideas.

## Designing Navigation
- Concise
- Clear
- Selective



## The ABC of Programming
- JS can be used to select any element inside a webpage.
- It can select all elements of the same class
- find out whats inside the tag of select elements
- it makes web pages more interactive
- JS can modify the content on the page.
- it can made the webpage feel like its responding to the reader
    - event listener

### Steps on how to start coding
1. Define the goal
1. Design the script
1. Code each step

### How to use Objects & Methods
- Typical javascript method call
- `[object].[methodname]([parameters])`
- Javascript runs where its found in HTML
    - it can be run inline `<script>[javascriptCode]</script>`
    - or it can be run from an external file
        - `<script src="[[directory/]script.js]"></script>`

### Summary
- A script is a series of instructions that the computer can follow in order to achieve a goal.
- Each time the script runs, it might only use a subset of all the instructors
- Computers approach tasks in a different way than humans , s o your instructions must let the computer solve the task programmatically.
- To approach writing a script, break down your goal into a series of tasks and then work out each step needed to complete that task (a flowchart can help).