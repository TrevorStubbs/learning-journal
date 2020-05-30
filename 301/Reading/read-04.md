# Read: 04 - Responsive Web Design and Regular Expressions
#### 5/30/20

- [CSS Grid Garden](https://cssgridgarden.com/)
- [RegExr](https://regexr.com/)
- [Regex Tutorial](https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285)
- [Regex 101](https://regex101.com/)
- [CSS Grid Reference](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Responsive design with CSS Grid](https://medium.com/samsung-internet-dev/common-responsive-layouts-with-css-grid-and-some-without-245a862f48df)

## CSS Grid Garden
- *Complete*
## RegExr 
## RegEx Cookbook
### Anchors 
- `^` start and `$` end
- `^`The end`$` - matches exactly
### Quantifiers 
- `*` `+` `?` and `{}`
### OR operator 
- `|` or `[]`
### Character classes
- `\d` (digit) `\w` (word) `\s` (whitespace) and `.`(any character)
- `\D` non single digit
### Flags
- Regex usually comes within /abc/.
- /g - global
- /m - multi-line
- /i - insensitive
### Grouping and capturing
- ()
### Bracket expressions
- []
### Greedy and Lazy Match
## Regex 101
- I like this one better.
## Complete guide to Grid
### Intro
- Flex box is for 1 dimensional work
- Grid is for 2D
### Terminology
- Grid Container
    - the parent container of everything in the grid
- Grid Item
    - the child inside the container
- Grid line
- Grid cell
- Grid track
- Grid Area
### Properties of Parent
- display
    - grid
    - grid-inline
- grid-template-columns/grid-template-rows
    - track-size
    - line-name
- grid-template-areas
    - grid-area-name
- grid-template
    - shorthand
- justify-items
    - start
    - end
    - center
    - stretch
- align-items
    - start
    - end
    - center
    - stretch
- place-items
- justify-content
    - start
    - end
    - center
    - stretch
    - space-around
    - space-between
    - space-evenly
- align-content
    - start
    - end
    - center
    - stretch
    - space-around
    - space-between
    - space-evenly
- place content
- grid-auto-columns / grid-auto-rows
- grid-auto-flow
- grid
### Properties for the Children
- grid-column-start
- grid-column-end
- grid-row-start
- grid-row-end
- grid-column
- grid-row
- grid-area
- justify-self
    - start
    - end
    - center
    - stretch
- align-self
    - start
    - end
    - center
    - stretch
- place-self