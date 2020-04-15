# Read: 04 - Structure web pages with HTML
##### 4/14/20

# Process & Design

### Requirements
- Read 18
- Skim 1
- Read Ch 17

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

# Structure
### The structure of the page will influence how it will be consumed
- Newspaper is different from an Insurance company
    - but they still follow the basic parts of a document
- HTML is made up of elements usually made with 2 tags.
    - `<p>`Words`</p>`
     
    ```html
    <p lang="en-us></p>

# HTML5 Layout
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