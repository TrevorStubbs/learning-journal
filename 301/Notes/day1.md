# Day 1 
#### 6/1/20

## Benefit of CF
- we are doers
- we are learners

## Expectations
- Set a schedule. Stick with it. Don't overwork yourself
    - get up after an hour
- Do the Prep-work
- 90% to pass
- 90% attendance required
- No Assignments in project week
- Instructor approval required to pass

## Emotional Intelligence - EQ
- 20% increase in pay

## Stereotypes
### Where do they come from?
- Family
- Community
- Religion
- Marketing
- Movies

## Unconscious Bias
- Implicit Bias

1. conformity: Groupthink
1. Beauty Bias: Perceived Successful
1. Affinity Bias: Warmed by same-ness
1. Similarity Bias: Only open to seeing ourselves in others
1. Confirmation Bias: Search for info to confirm perception
1. Halo Effect: 1 great thinking gives a glow
1. Horns Effect: Put off by something them assume
1. Contrast Effect: Comparing to others
1. Attribution Bias: Owning wins and assigning losses

## Const / let
``` JavaScript
const name = 'bob' 
name = 'ben' //not allowed

const arr = [1,3,4,5];
arr.push(5); // allowed

const person = {name: sue, age: 12};
person.hair = 'blue'; // ALLOWED
```

- outer casing is what keeps it a `const`

## SMACCS
    - a framework for organizing CSS files
- Base - default rules
- Layout - general rules
- Modules - rules that target smaller reusable pieces
- State - rules that are meant for providing styling for different app states
- Theme - overall theme

## Responsive Design
- the preferred way to build a site for multiple screen sizes
    - check the screen 
- HTML
    - `<meta name="viewport" content="width=device-width, initial-scale=1">`
- CSS     
    ``` CSS
    @media only screen and (max-width:500px){ /* max or min is inclusive */
        // css here for devices with a max width of 500px    
    }
    ```

    - box-sizing: border-box; - includes the border inside the border box
    - line-height: [height of box] - to center vertically

## forEach()
- `arr.forEach(callback(currentValue [, index [, array]])[, thisArg])`