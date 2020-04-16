# Read: 07 - Programming with JavaScript
#### 4/16/20

## Intro
#### Access
#### Modify
#### Program
#### React

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

### From Steps to Code
1. Vocabulary
    - Words the comp understands
1. Syntax
    - How you put word together

- Computers are the dumbest
    - they have to be told exactly what to do
    - they can to infer anything
    - you have to 'think' like a comp

- Sketch out the tasks in a flowchart

### Summary
- A script is a series of instructions that the computer can follow in order to achieve a goal.
- Each time the script runs, it might only use a subset of all the instructors
- Computers approach tasks in a different way than humans , s o your instructions must let the computer solve the task programmatically.
- To approach writing a script, break down your goal into a series of tasks and then work out each step needed to complete that task (a flowchart can help).


## Expressions and Operations:
- An expressions evaluates into a single value.
    - `var color = 'beige';`
    - `var area = 3 * 2;`

- Operators
    - `=` assignment operator
    - `+` arithmetic operator
    - `'[char]'` string operator
    - `>` Comparison operator
    - `&&` logical operator

### Arithmetic Operators
Name | Operator | Purpose
--- | --- | ---
Addition | `+` | Adds one value to another
Subtraction | `-` | Subtracts 1 value from another
Division | `/` | Divides two values
Multiplication | `*` | Multiplies 2 values
Increment | `++` | Adds 1 to current value
Decrement | `--` | Subtracts 1 from current value
Modulus | `%` | Divides 2 values and returns the remainder

### String Operator
- Turn anything into a string by wrapping it in `""`.

## Functions
- You can group expressions together into a function

- Here is an example
```javascript
function updateMessage(){
    var el = document.getElementById('message');
    el.textContent= msg;
}
```
- You can activate the function at any time by calling it name
```javascript
updateMessage();
```

- How to write a function
```javascript
// format is function keyword
// function name ()
// statements;
function [functionName]([parametersIfNeeded]){
    [expression];
    [return] [returnValue]; // not required if the function doesn't return anything
}
```

- How to call a function
```javascript
//call the function's name followed by '();'
[functionName]([arguments]);
```

- if you need a value out of a function you need to use the `return` keyword at the end
