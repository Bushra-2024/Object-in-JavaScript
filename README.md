# Object-in-JavaScript

***First, look at the picture to understand object properties and methods.***


![image](https://github.com/user-attachments/assets/ef314f1d-b11e-44c9-a3c6-fb23aca2900d)


An `object` in JavaScript is a collection of properties. Each property is made up of a key (also called a name) and a value.
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
  age: 30
};

// Accessing properties using dot notation
console.log(person.name); // Output: John
console.log(person.age);  // Output: 30

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


## `for...in`

The JavaScript for in statement loops through the properties of an Object and It allows you to access each key or property name of an object.:

```
Example -
for (key in object) {
  // code block to be executed
}
```

### difference between `for...in` and `for...of`

**`for...of`**: Goes through **values** (items) in an array or other collections.  
Example: `for (let value of [10, 20, 30])` → gives `10`, `20`, `30`.

**`for...in`**: Goes through **keys** (property names) in an object.  
Example: `for (let key in {a: 1, b: 2})` → gives `'a'`, `'b'`.  


-----------

# Keyword `this`
The `this` keyword in JavaScript is a special reference that changes based on how and where it is used. It refers to the context in which the current code is being executed. 

---

### **What is `this` in JavaScript?**
`this` is a dynamic keyword that refers to an object, and its value depends on:
1. **Where the code is written** (global scope, function, or class).
2. **How the function is called** (as a method, standalone, or with `new`).

---

### **How Does `this` Work in Different Contexts?**

1. **Global Scope**:
   - In the global context (outside any function or object):
     - In **non-strict mode**, `this` refers to the **global object** (`window` in browsers, `global` in Node.js).
     - In **strict mode**, `this` is `undefined`.

   ```javascript
   console.log(this); // In browser: Window object
   "use strict";
   console.log(this); // undefined
   ```

2. **Inside Regular Functions**:
   - **Non-strict mode**: `this` refers to the global object.
   - **Strict mode**: `this` is `undefined`.

   ```javascript
   function showThis() {
     console.log(this);
   }
   showThis(); // In browser: Window object (non-strict), undefined (strict)
   ```

3. **Object Methods**:
   - When a function is called as a method of an object, `this` refers to the **object** that owns the method.

   ```javascript
   const obj = {
     name: "JavaScript",
     showThis: function () {
       console.log(this); // Refers to obj
     },
   };
   obj.showThis(); // Logs obj
   ```

4. **Arrow Functions**:
   - Arrow functions **don’t have their own `this`**. Instead, they inherit `this` from the **surrounding lexical scope** (where the arrow function is defined).

   ```javascript
   const obj = {
     name: "Arrow",
     showThis: () => {
       console.log(this); // Refers to the outer context (global object or undefined in strict mode)
     },
   };
   obj.showThis(); // Logs Window (or undefined in strict mode)
   ```

5. **In Anonymous Functions**
The value of `this` in an **anonymous function** depends on how the function is called:

  1. **Called in Global Scope**:  
   - Non-strict mode: `this` refers to the global object (`window`).
   - Strict mode: `this` is `undefined`.

```javascript
const anonFunc = function () {
console.log(this); // Logs: Window (non-strict) or undefined (strict)
};
anonFunc();
```

  2. **Used as a Method**:  
   If assigned to an object and then called, `this` refers to the object.

```javascript
const obj = {
method: function () {
console.log(this); // Logs: obj
},
};
obj.method();
```

