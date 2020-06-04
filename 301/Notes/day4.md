# Day 4: 
#### 6/4/20

## Regex
- used on strings
- between `//`
- use `/g` sparingly

## Code Challenge
- `npm i` in the challenge directory
- maybe `npm install cheerio -g`

## Grid
- display: grid | inline-grid
- grid-template-columns:
- grid-template-rows:
### Demo
- need to make my site more mobile first

## Interview Practice
- Problem Domain
- Ask Questions
    - Interviewers will leave info out on purpose
    - Ask about edge cases
- Identify the inputs and outputs
- Visualization
    - Draw pictures
    - arrows
    - draw an example of the input
    - draw an example of the output
    - draw how to get from the input to the output
- Algorithm
    - In word describe how to solve the problem
    - Write down the options what would break the code
- Pseudo Code
    - code without the syntax
- Write the code
- Verification
    - step through the code using the visualization as a guide
- Big O
    - How can we make the code more efficient





write a function that take in an array sort it by length

- input will always be a string
- no max length

- input is an unstorted array
- output is a sorted array

arr = [12, 253, 3, 3.7]

const interviewQuestion = (arr) => {
    for(let i = 0; i< arr.length; i++){
        arr[i] = arr[i].toString();
    }
    arr.sort((a,b) => {
        a = a.length;
        b = b.length;
        return  a < b ? -1: 1;
    });
    for(let i = 0; i < arr.length; i++){
        arr[i] = Number(arr[i]);
    }
    return arr;
};