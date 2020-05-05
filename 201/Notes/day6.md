# Day 6 Notes 
#### 5/4/20

- template literal - `${}`

```JavaScript
function multiplyAnyArray(dynamicArray) { //eslint-disable-line
  var reducer = (accumulator, currentValue) => multiply(accumulator, currentValue)[0];
  return [dynamicArray.reduce(reducer), 'The numbers ' + dynamicArray +' have a product of ' + dynamicArray.reduce(reducer) + '.'];
}
```
- Legality of Image use:
    - unsplash.com

- Size the photo to its on page size
- when sizing the photo only choose either the width or the height

```JavaScript
// key value pairs

school: 'Code Fellows';

var ilya = {
  name: 'Ilya',
  eyeColor: 'blue',
  hair: ['pink', 'blue', 'red', 'brown'],
  isLoud: true,
  age: 11,
  father: {
    name: 'Adam',
    eyeColor: 'blue',
    hair: 'light brown',
    isLoud: false,
    age: 40, 
  },
  dancing: function(){
    console.log(`${this.name} is dancing`);
  }
};

var adam = {
  name: 'Adam',
  eyeColor: 'blue',
  hair: 'light brown',
  isLoud: false,
  age: 40
};

// Accessing properties on an object
// 1. dot notation
console.log(ilya.name);

console.log(ilya.father.eyeColor);
ilya.dancing();

// 2. bracket notation
console.log(ilya['name']);


// contextual this. reference its own object
// looping through an object
var myPets = [
  {
    name: 'cookie',
    age: 9
  },
  {
    name: 'tangerine',
    age: 6
  },
  {
    name: 'malaki',
    age: 4
  }
];

var petNames = [];

// loop through pets and push names into petNames
for(var i = 0; i < myPets.length; i++){
  petNames.push(myPets[i].name);
}

console.log(petNames);


```

The DOM => JS interacts with the HTML

- `getElementsByClassName` = produces an Array
- `getElementById` = produces an single item

1. select the parent element
1. create the new element
1. give content to the new element
1. append it to the parent


---
Salmon Cookies:
Given
- object literals for each store
- min customer per hour
- max customer per hour
- avg cookie per customer

Generated
- array - holds average number of customers for every hour the store is open based off of the min and max using math.random
- array - average number of cookies sold per hour. - multiply the random customers by the average cookie sale. 

- append this to the DOM as a list