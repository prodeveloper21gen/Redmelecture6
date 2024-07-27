![image](https://github.com/user-attachments/assets/a127b8dc-7d73-405d-8bc8-d038c6af38eb)

# JavaScript Objects

## Overview

In JavaScript, an object is a collection of key-value pairs where each key is a string (or a symbol) and each value can be any data type, including other objects. Objects are fundamental to JavaScript and are used to store and manipulate data. They can represent real-world entities, such as a user or a product, and can be used to group related data and functions together.

## Creating Objects

There are several ways to create objects in JavaScript:

### Object Literal Notation

The simplest way to create an object is by using object literal notation:

```javascript
const person = {
  name: 'John Doe',
  age: 30,
  greet: function() {
    console.log('Hello, my name is ' + this.name);
  }
};

### Constructor Function

You can also create objects using a constructor function:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
  this.greet = function() {
    console.log('Hello, my name is ' + this.name);
  };
}

const person = new Person('John Doe', 30);
```

### Object.create()

The `Object.create()` method creates a new object with the specified prototype object and properties:

```javascript
const proto = {
  greet: function() {
    console.log('Hello, my name is ' + this.name);
  }
};

const person = Object.create(proto);
person.name = 'John Doe';
person.age = 30;
```
```javascript
const propName = 'name';
console.log(person[propName]); // John Doe
```

## Methods

Objects can have methods, which are functions defined as properties of the object:

```javascript
const person = {
  name: 'John Doe',
  age: 30,
  greet() {
    console.log('Hello, my name is ' + this.name);
  }
};

person.greet(); // Hello, my name is John Doe
```
### Object.keys() and forEach

```javascript
Object.keys(person).forEach(key => {
  console.log(key + ': ' + person[key]);
});
```

## Inheritance and Prototypes

JavaScript objects have a prototype chain that allows for inheritance. Every object has a prototype object that can be used to share properties and methods among objects:

```javascript
const animal = {
  eat() {
    console.log('Eating');
  }
};

const dog = Object.create(animal);
dog.bark = function() {
  console.log('Barking');
};

dog.eat(); // Eating
dog.bark(); // Barking
```
