# Read: 08 - Operators and Loops
#### 4/16/20

## Comparison Operators:
- `==` is equal to
- `===` is strict equal to
- `!=` not equal to
- `!==` strict not equal to
- `>` greater than
- `<` less than
- `>=` greater than or equal to
- `<=` less than or equal to

## Logical Operators
- `&&` and
- `||` or
- `!` not

## Loops
- sometimes you need to have the comp do something repeatedly
- 3 types of loops
    - for
        - When you know how many times you need to loop
    - while
        - when you don't know how many times you need to loop
    - do while
        - like a while loop but it will do the expression first before it starts looping.

### `For` Loops
- `for (var [counter] = [initialLoopValue]; [counter] < [stopping point]; [incrementor])

```javascript
for (var i = 0; i < 10; i++){
    [expression to be looped];
}
```

- Loop keywords
    - `break` will tell the program to stop looping.
    - `continue` will tell the program to continue looping

### `While` Loops
- a while loop uses to conditional statement to tell it what to do
    - `while(x === true) {[expression];}`
- a while loop will continue to do something along as the expression is true
- Usually you have to build your own counter inside the loop
    - while loops are more likely to be in a never ending loop.

```javascript
var x = 0;
while(x >= 10){
    console.log("I am number" + x + ".");
    x++;
}
```

- if `x` was already `>` than 10 then the loop won't even run.
- So sometimes you want to have it run at least once and thats whey you'd use a `do while` loop
```javascript
var x = 15;
do while(x>=0){
    console.log("Hello World!");
    x++;
}
```
- since x was already above 10 this code will only run once.


