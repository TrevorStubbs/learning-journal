# Day 7 Notes
#### 5/5/20

```JavaScript
// var anderw = {
//   name: 'Andrew',
//   hair: 'brown',
//   eyes: 'blue',
//   shoeSize: 10.5,
//   student: true,
//   doingLab: function(){
//     console.log(`${this.name}is doing lab`);
//   }
// }

// Constructor funciton
function Student(name, hair, eyeColor, shoeSize){
  this.name = name;
  this.hairColor = hair;
  this.eyeColor = eyeColor;
  this.shoeSize = shoeSize;
  this.doingLab = function(){
     console.log(`${this.name} is doing lab`);
  }
}
```

- Literals us `:` and `,`
- Constructors use `=` and `;`

turn the functions into protoyes and pull them out of the constructor function

## Tables
- Turn the lists into a table
- table
  - tbody
    - tr
      - th
      - th
    - tr
      - td
      - td