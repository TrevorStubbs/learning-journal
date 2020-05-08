# Day 9 Notes
#### 5/7/20 

- required - for a form to be entered

## Events
- Events: FIRED or RAISED
- Code: TRIGGERED
- Event types;
    - page load
    - submit
    - error
    - resize
    - keyup

- Listeners => code that is waiting for an event to occur
- Handlers => code taht is going to take action when an event is fired.
- Bind => bind and event to a listener
    - (old) `<div onSubmit="handleEvent()">`
    - (old) 
    ```JavaScript 
    element.onevent = funcitonName; 
    button(document.getElementById('button')).onsubmit = handleEvent;
    ```
    - (this way) DOM level 2 event handlers 
    ``` JavaScript
    element.addEventListener('event', functionName);
    ```

- Asynchronous code: code that is run out of order

- Event bubbling - bubbles outward. Can put a listener on the parent element

- Event capturing - out to in. (dont use this)