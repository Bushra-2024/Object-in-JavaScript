# Object-in-JavaScript

***First, look at the picture to understand object properties and methods.***

<img src="https://miro.medium.com/v2/resize:fit:1400/1*_3XepNDk6wDs18gvzeOHVA.jpeg">


An `object~ in JavaScript is a collection of properties. Each property is made up of a key (also called a name) and a value.

    - The key is a string (or a symbol), and the value can be any type, including primitive values (like numbers or strings), other objects, or functions. 
    - Objects work with defined keys, meaning you can use specific names to access or modify their properties.


In contrast:

An array is a collection of elements where each element has an index (a number starting from 0). Arrays are typically used when you want to store ordered data, and they are dependent on their index.


So, for objects:

Think of them as key-value pairs, like a dictionary.
```js
Example
const person = {
  name: "John",
  age: 30,
  isStudent: false
};
console.log(person.name); // Output: "John"
```
Objects are flexible and can store multiple types of data, making them great for modeling real-world entities.


# Object Structure
<img src="https://miro.medium.com/v2/resize:fit:720/1*IlP9iTPaGkx4PWYwHejDGw.png">



## Here are three ways to access and display an object in JavaScript using the person object as an example:

1. Calling a Function (Method)
If the object has a method (a function as a property), you can call it to display the object or its properties.
```js
const person = {
  name: "John",
  age: 30,
  greet: function() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
};

// Calling the method to show the person's information
person.greet(); // Output: Hello, my name is John and I am 30 years old.
```

2. Using Bracket Notation
Bracket notation allows you to access properties of an object using a string key. This is useful when the property name contains spaces or is dynamic.
```js
const person = {
  name: "John",
  age: 30
};

// Accessing properties using bracket notation
console.log(person["name"]); // Output: John
console.log(person["age"]);  // Output: 30
```

3. Destructuring Assignment
Destructuring is a convenient way to extract values from an object and assign them to variables. It simplifies accessing multiple properties at once.
```js
const person = {
  name: "John",
  age: 30
};

// Destructuring to get specific properties
const { name, age } = person;

console.log(name); // Output: John
console.log(age);  // Output: 30
```



<img src="https://i.ytimg.com/vi/kX5NyqXtl6Y/maxresdefault.jpg">
