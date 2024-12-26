# Object-in-JavaScript

***First, look at the picture to understand object properties and methods.***

<img src="https://miro.medium.com/v2/resize:fit:1400/1*_3XepNDk6wDs18gvzeOHVA.jpeg">


![image](https://github.com/user-attachments/assets/ef314f1d-b11e-44c9-a3c6-fb23aca2900d)


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


Here’s an overview of three commonly used **Object methods** in JavaScript, along with explanations and examples:

---

### 1. **`Object.keys()`**
- **Description**: Returns an array of all the keys (property names) of the object.
- When you want to get a list of the property names in an object.

**Example**:
```javascript
const person = { name: "Alice", age: 25, city: "New York" };

const keys = Object.keys(person);
console.log(keys); // Output: ["name", "age", "city"]
```

---

### 2. **`Object.values()`**
- **Description**: Returns an array of all the values of the object.
- When you want to extract only the property values from an object.

**Example**:
```javascript
const person = { name: "Alice", age: 25, city: "New York" };

const values = Object.values(person);
console.log(values); // Output: ["Alice", 25, "New York"]
```

---

### 3. **`Object.entries()`**
- **Description**: Returns an array of key-value pairs from the object, where each key-value pair is an array.
- When you need both keys and values, often for iterating through the object.

**Example**:
```javascript
const person = { name: "Alice", age: 25, city: "New York" };

const entries = Object.entries(person);
console.log(entries); 
// Output: [["name", "Alice"], ["age", 25], ["city", "New York"]]

// Iterating through entries
entries.forEach(([key, value]) => {
    console.log(`${key}: ${value}`);
});
// Output:
// name: Alice
// age: 25
// city: New York
```

---


### **What is Destructuring in Objects?**
- Destructuring allows you to **extract properties from an object and assign them to variables**, making your code cleaner and easier to understand.

---

### **Basic Syntax**:
```javascript
const { key1, key2 } = objectName;
```

---

### **Example 1: Basic Destructuring**
```javascript
const person = { name: "Alice", age: 25, city: "New York" };

const { name, age } = person;

console.log(name); // Output: Alice
console.log(age);  // Output: 25
```

---

### **Example 2: Renaming Variables**
You can rename the variables while destructuring if you don’t want to use the exact property names:
```javascript
const person = { name: "Alice", age: 25, city: "New York" };

const { name: fullName, age: yearsOld } = person;

console.log(fullName); // Output: Alice
console.log(yearsOld); // Output: 25
```

---

### **Example 3: Providing Default Values**
If a property doesn’t exist in the object, you can set a default value:
```javascript
const person = { name: "Alice", age: 25 };

const { name, city = "Unknown" } = person;

console.log(name); // Output: Alice
console.log(city); // Output: Unknown
```

---

### **Example 4: Nested Destructuring**
If an object contains another object, you can destructure the nested properties:
```javascript
const person = { 
    name: "Alice", 
    address: { city: "New York", zip: "10001" } 
};

const { address: { city, zip } } = person;

console.log(city); // Output: New York
console.log(zip);  // Output: 10001
```

