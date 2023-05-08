# JavaScript Notes

## Table Of Contents

- [Arrays](#arrays)
  * [Array Methods](#array-methods)
- [Objects](#objects)

## Arrays

### Array Methods
<hr>

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

The `some()` method is used to check whether any element in an array passes a provided function. Essentially, it tests whether at least one element in the array passes the test implemented as provided by the callback function.

```javascript
const isBelowThreshold = (currentValue) => currentValue < 40;

const array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// Expected output: true
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
