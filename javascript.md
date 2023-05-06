# JavaScript Notes

- [Objects](#objects)

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


