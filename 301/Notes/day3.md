# Day 3
#### 6/3/20

- TDD Test driven development
    - Write tests first then write the code make the tests fast
- You can stack `.then`

## Sort Function
``` JavaScript
//Number sort
const myArr = [23, 1, 24, 3];

myArr.sort()

console.log(myArr)

myArr.sort((a,b) =>{
  console.log('a', a, 'b', b);
  console.log(a-b);
})

// a-b small to big
// b-a big to small

// Sort by String
const stringArray = ['bob', 'Able', 'Zed', 'zed', 'apeble'];

stringArray.sort();

stringArray.sort((a,b) => {
  a = a.toLowerCase();
  b = b.toLowerCase();
  if (a > b){
    return 1;
  } else if (a < b){
    return -1;
  } else {
    return 0;
  }
});

console.log(stringArray);


// Ternarys
// normal
// if(a<b){
//   return 1;  
// } else {
//   return -1;
// }

//Ternary
// return a < b ? 1 : -1;

// return a < b ? 1:
//        b < c ? 2:
//        c < d ? 3:
//        4;

// Ternary has to return something.



const newArray = ['bob', 'Able', 'Zed', 'zed', 'able'];

newArray.sort((a,b) => {
  return a.name > b.name ? 1:-1;
})
```

## Flexbox

## Templating

```JavaScript
//different way to do a constrictor

// get all the keys from the data and assigning it to the key
function Hood(obj){
    for (let key in obj){
        this[key] = obj[key];
    }
    hood.push(this);
}
```

``` JavaScript
//get the template
Hood.prototype.toHtml = function(){
    // 1. Get the template from the html
    let template = $('#neighborhood-template').html();
    // 2. Use Mustache to build the new html by merging the template with the data
    let html = Mustache.render(template, this);
    // 3. Return the "html" from this method
    return html;
}
```

``` JavaScript
hoods.forEach(hood => {
    // Create the html
    let hoodHtml = hood.toHtml();
    //append it to the page
    $('#neighborhoods').append(hoodHtml);
});
```