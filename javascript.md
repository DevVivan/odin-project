# JavaScript Notes

## Table Of Contents

- [Arrays](#arrays)
  * [Array Methods](#array-methods)
    + [Array.prototype.filter()](#arrayprototypefilter--)
- [Objects](#objects)
  * [Using 'object constructor' syntax](#using--object-constructor--syntax)
  * [Using 'object literal' syntax](#using--object-literal--syntax)
  * [Adding properties to an object](#adding-properties-to-an-object)
  * [Removing properties from an object](#removing-properties-from-an-object)
  * [Multiword property names](#multiword-property-names)
  * [Square brackets](#square-brackets)
  * [Property existence test](#property-existence-test)
  * ['For in' loop](#-for-in--loop)
  * [What is "this"?](#what-is--this--)

## Arrays

### Array Methods

#### Array.prototype.filter()

The `filter` method can be used to filter down to just the elements from a given array that pass the test implemented by the provided function.

```javascript
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);

console.log(result);
// Expected output: Array ["exuberant", "destruction", "present"]
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
