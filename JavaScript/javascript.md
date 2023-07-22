# JavaScript Notes

## Table Of Contents

- [Strings](#strings)
  * [String Methods](#string-methods)
- [Arrays](#arrays)
  * [Array Methods](#array-methods)
- [Objects](#objects)
- [Object Constructors](#object-constructors)
- [Factory Functions](#factory-functions)
- [The Module Pattern](#the-module-pattern)

## Strings

### String Methods
<hr>

#### Extracting string parts

There are 3 main ways to extract parts from a string. These are:

- `charAt(position)` - returns the character at a specified index (position) in a string.
- `charCodeAt(position)` - returns the unicode of the character at a specified index in a string.
- Property Access [ ] 

#### Extracting string characters

There are 3 main ways to extract parts from a string. These are:

- `slice(start, end)` - extracts a part of a string and returns the extracted part in a new string.
- `substring(start, end)` - similar to slice, but, start and end values less than 0 are treated as 0 in substring().
- `substr(start, length)` - similar to slice, but, the second parameter specifies the length of the extracted part.

#### Replacing a string's content

- `replace() // only replaces the first match`
- `replaceAll()`

```javascript
// replace()
let text = "Please visit Microsoft and Microsoft!";
let newText = text.replace("Microsoft", "W3Schools");

// replaceAll()
text = text.replaceAll(/Cats/g,"Dogs");
text = text.replaceAll(/cats/g,"dogs");
```

#### Converting a string to uppercase or lowercase

- A string is converted to upper case with `toUpperCase()`
- A string is converted to lower case with `toLowerCase()`

#### Converting a string to an array and back

To convert a string to an array, we can use the `split()` method. 

```javascript
text.split(",")    // Split on commas
text.split(" ")    // Split on spaces
text.split("|")    // Split on pipe

text.split("") // will return an array of **SINGLE** characters
```

To convert an array to a string, we can use the `array.prototype.join()` method.

```javascript
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// Expected output: "Fire,Air,Water"

console.log(elements.join(''));
// Expected output: "FireAirWater"

console.log(elements.join('-'));
// Expected output: "Fire-Air-Water"
```

#### Other methods

- `concat()` - To join two or more strings.
- `trim()` - The trim() method removes whitespace from both sides of a string.
- `trimStart()` - The trimStart() method works like trim(), but removes whitespace only from the start of a string.
- `trimEnd()` - The trimEnd() method works like trim(), but removes whitespace only from the end of a string.
- `padStart()` - The padStart() method pads a string from the start.
- `padEnd()` - The padEnd() method pads a string from the end.

## Arrays

### Array Methods
<hr>

| Method Name     | Syntax                      | Function                                                                                               |
|-----------------|-----------------------------|--------------------------------------------------------------------------------------------------------|
| Filter          | Array.prototype.filter()    | To create a new array filled with elements that pass a test provided by a function                     |
| Map             | Array.prototype.map()       | To iterate over an array and perform a transformation or computation.                                  |
| Sort            | Array.prototype.sort()      | To return a sorted list of the specified iterable object                                               |
| Reduce          | Array.prototype.reduce()    | To reduce an array to a single value by passing a callback function on each element of the array       |
| Some            | Array.prototype.some()      | To test whether at least one element in the array passes the test implemented by the provided function |
| Every           | Array.prototype.every()     | To check if all the elements of the array satisfy the callback function condition or not.              |
| Find            | Array.prototype.find()      | To return the first element in the provided array that satisfies the provided testing function.        |
| Find Index      | Array.prototype.findIndex() | To return the index of the first element in an array that satisfies the provided testing function.     |
| Reverse          | Array.prototype.reverse()    | To reverse an array in place and returns the reference to the same array, the first array element now becoming the last, and the last array element becoming the first.

#### Array.prototype.filter()

The `filter()` method can be to loop through an array and test for *something* and then create a new array with only the matching items. Essentially, it creates a news array filled with the elements that pass a test provided by a function.

```javascript
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);

console.log(result);
// Expected output: Array ["exuberant", "destruction", "present"]
```

#### Array.prototype.map()

The `map()` method can be to *do something* to every item in an array and then create a new array with the changed items. Essentially, it is used to iterate over an array and manipulate or change the items.

```javascript
const array1 = [1, 4, 9, 16];

// Pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// Expected output: Array [2, 8, 18, 32]
```

#### Array.prototype.sort()

The `sort()` method takes an array and, well, *sorts it*. Essentially, itn sorts the elements of an array in place and returns the reference to the same array, now sorted.

```javascript
const items = [
  { name: "Edward", value: 21 },
  { name: "Sharpe", value: 37 },
  { name: "And", value: 45 },
  { name: "The", value: -12 },
  { name: "Magnetic", value: 13 },
  { name: "Zeros", value: 37 },
];

// sort by value
items.sort((a, b) => a.value - b.value);

// sort by name
items.sort((a, b) => {
  const nameA = a.name.toUpperCase(); // ignore upper and lowercase
  const nameB = b.name.toUpperCase(); // ignore upper and lowercase
  if (nameA < nameB) {
    return -1;
  }
  if (nameA > nameB) {
    return 1;
  }

  // names must be equal
  return 0;
});
```

#### Array.prototype.reduce()

The `reduce()` method is used to *reduce* a complete array into a single value by performing some tasks to each element in the array. Essentially, it executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.

```javascript
const array1 = [1, 2, 3, 4];

// 0 + 1 + 2 + 3 + 4
const initialValue = 0;
const sumWithInitial = array1.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  initialValue
);

console.log(sumWithInitial);
// Expected output: 10
```

#### Array.prototype.some()

The `some()` method is used to check whether all element in an array pass a provided function. Essentially, it tests whether all elements in the array pass the test implemented by the provided function. 

```javascript
const array = [1, 2, 3, 4, 5];

// Checks whether an element is even
const even = (element) => element % 2 === 0;

console.log(array.some(even));
// Expected output: true
```

#### Array.prototype.every()

The `every()` method is used to check whether any element in an array passes a provided function. Essentially, it tests whether at least one element in the array passes the test implemented as provided by the callback function.

```javascript
const isBelowThreshold = (currentValue) => currentValue < 40;

const array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// Expected output: true
```

#### Array.prototype.find()

The `find()` method returns the first element in the provided array that satisfies the provided testing function. It loops through an array, checks whether the element passes the provided function, and the **FIRST** element it finds that satisfies it, is the element provided.

```javascript
const array1 = [5, 12, 8, 130, 44];

const found = array1.find(element => element > 10);

console.log(found);
// Expected output: 12
```

#### Array.prototype.findIndex()

The `findIndex()` method returns the index of the first element in an array that satisfies the provided testing function. If no elements satisfy the testing function, -1 is returned.

```javascript
const array1 = [5, 12, 8, 130, 44];

const isLargeNumber = (element) => element > 13;

console.log(array1.findIndex(isLargeNumber));
// Expected output: 3
```

## Objects

Objects are one of the eight data types in JavaScript that are used to store keyed connections of data. They usually contain an optional list of properties - a property being a '`key:value` pair'.

There are two main ways used to create empty objects, each with their own different syntaxes.

### Using 'object constructor' syntax

```javascript
let user = new Object();
```

### Using 'object literal' syntax

```javascript 
let user = {};
```

The **object literal** syntax is often used and properties can be stored in the form of 'key:value' pairs inside `{...}`. For instance, an object created using the 'object literal' syntax with a couple of properties would look like the example below. Inside the `user` object, there are two 'key:value' pairs separated by commas with the name `'name'` & value `'John'`, and the name `'age'` & value `30` respectively.

```javascript
let user = {     // creation of object
  name: "John",  // key "name" should store the value "John"
  age: 30        // key "age" should store the value 30
};
```

### Adding properties to an object

To add an object property we can use dot notation, for example, in the given code above, to add a property with name `'gender'` & value `'male'`, we would do:

```javascript
user.gender = 'male';
```

### Removing properties from an object

```javascript
delete user.age;
```

### Multiword property names

If you wish for your property name to be multiword, i.e - more than one word, the property name must be quoted. 

```javascript
let user = {
  name: "John",
  age: 30,
  "likes birds": true  // multiword property name must be quoted
};
```

### Square brackets

For multiword property names, the dot notation for access does not work, therefore, we can use square brackets instead. 

```javascript
let user = {};

// set
user["likes birds"] = true;

// get
alert(user["likes birds"]); // true

// delete
delete user["likes birds"];
```

### Property existence test

To check if a property is `in` an object, we can use the `in` operator.

```javascript 
let user = { name: "John", age: 30 };

alert( "age" in user ); // true, user.age exists
alert( "blabla" in user ); // false, user.blabla doesn't exist
```

### 'For in' loop 

```javascript
for (prop in object) {
  // executes the body for each key among object properties
}
```

Keep in mind that when alerting an object, integer properties will be sorted/ordered, and others will appear in creation order.

```javascript
let codes = {
  "49": "Germany",
  "41": "Switzerland",
  "44": "Great Britain",
  // ..,
  "1": "USA"
};

for (let code in codes) {
  alert(code); // 1, 41, 44, 49
}
```

### What is "this"?

The `this` keyword refers to the current object the code is being written inside. For instance:

```javascript
const person1 = {
  name: "Chris",
  introduceSelf() {
    console.log(`Hi! I'm ${this.name}.`);
  },
};

const person2 = {
  name: "Deepti",
  introduceSelf() {
    console.log(`Hi! I'm ${this.name}.`);
  },
};
```

## Object Constructors

When we have a specific type of object we would like to duplicate, we should use object constructors as such:

```javascript
function Player(name, marker) {
  this.name = name
  this.marker = marker
}
```

Which we can use by calling the function with the `new` keyword:

```javascript
const player = new Player('steve', 'X')
```

### The prototype

All objects in JavaScript have a `prototype`. Stated simply, the `prototype` is another object that the original object inherits from, which is to say, the original object has access to all of its prototype’s methods and properties.

We can access an object's prototype using the `Object.getPrototypeOf()` function. This can also be done using the `__proto__` property of an object but this is deprecated now. In some areas, like legacy code, we might also come across `[[Prototype]]`. 

Just as we use `Object.getPrototypeOf()` to ‘get’ or view the prototype of an object, we can use `Object.setPrototypeOf()` to ‘set’ or mutate it. `Object.setPrototypeOf()` takes two arguments - the first is the one which inherits and the second argument is the one which we want the first argument to inherit from. 

As a rule of thumb, we should create object methods for a constructor using prototypes as such:

```javascript
Player.prototype.sayName = function() {
  console.log('Player')
}
```

## Factory Functions

Factories are simply plain old JavaScript functions that return objects for us to use in our code. Using factories is a powerful way to organize and contain the code we’re writing. Factory functions are similar to object constructors but they simply set up and return the new object when you call the function as such:

```js
const personFactory = (name, age) => {
  const sayHello = () => console.log('hello!');
  return { name, age, sayHello };
};

const jeff = personFactory('jeff', 27);

console.log(jeff.name); // 'jeff'

jeff.sayHello(); // calls the function and logs 'hello!'
```

### Object shorthand

We can also use an object shorthand when creating an object where we are referring to a variable that has the exact same name as the object property we're creating like so:

```js
return {name: name, age: age, sayHello: sayHello}; 
return {name, age, sayHello}; // condensed object shorthand
```

## The Module Pattern

Modules are actually very similar to factory functions and the main difference is how they’re created. The concept is simple: we write a function, wrap it in parentheses, and then immediately call the function by adding `()` to the end of it. They are an example of an  IIFE (Immediately Invoked Function Expression). This is an example:

```js
(function() {
  'use strict';
  // Your code here
  // All function and variables are scoped to this function
})();
```
