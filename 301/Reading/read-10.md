# Read: 10 - The Call Stack and Debugging
#### 6/7/20

- [The Call Stack defined on MDN](https://developer.mozilla.org/en-US/docs/Glossary/Call_stack)
- [Understanding the JavaScript Call Stack](https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/)
- [JavaScript error messages](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)
- [JavaScript errors reference on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors)

## The Call Stack
- It's the instruction sheet for the interpreter.
- When a function is called it gets added to the top of the call stack
- when the current function is finished its taken off the stack and the next function gets run
- if the stack takes up more space that it has assigned to it will cause a 'stack overflow'.
- Runs on LIFO - last in first out.

- when a function it invoked, the function, its parameters and variable are pushed onto the stack. 
- When the function finished it gets popped off the top of the stack.

## Error messages
### Types of error messages
- Reference Errors
    - When a variable is not yet declared.
    - Trying to access a poorly scoped variable
- Syntax errors
    - trying to parse an invalid object
    - forgetting `,` or `}` etc.
- Range Errors
    - trying to mainuplate something outside its range 
        - looking for and index of an array that is larger than the array
- Type errors
    - trying to work with incompatible types
### Debugging
- use console.log
- use breakpoints in the browser
### Call Stack
### Handling Errors
- try-catch blocks
```JavaScript
try{
    //do this
} catch(err){
    //show the err
}
```

### Tools
- quokka - code evaluator
- eslint - helps with style and flag possible errors along the way.
