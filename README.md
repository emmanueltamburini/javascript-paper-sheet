# JavaScript PaperSheet

This is a basic Express application written in TypeScript named PaperSheet.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Installation](#installation)
3. [Running the Application](#running-the-application)
4. [Project Structure](#project-structure)
5. [Index](#index)
6. [Resume](#resume)
7. [Testing](#testing)
8. [Linting](#linting)
9. [Additional Information](#additional-information)

## Prerequisites

Before you begin, ensure you have the following installed on your system:

1. Node.js (version 14 or higher)
   - Download and install from: <https://nodejs.org/>

2. npm (usually comes with Node.js)

## Installation

1. Install dependencies:

   ``` batch
   npm install
   ```

## Running the Application

1. To start the application, run:
  
   ``` batch
   npm start
   ```

2. The application should now be running. By default, it will be accessible at `http://localhost:3000`.

## Project Structure

- `package.json`: Contains project metadata and dependencies
- `app.ts`: Main application file
- `tsconfig.json`: TypeScript configuration file
- `dist/`: Directory containing compiled JavaScript files

## Index

This project serves as a foundation to explore various JavaScript concepts:

1. **JavaScript Fundamentals**
   - Variables and data types
   - Operators and expressions
   - Control structures (if/else, loops)
   - Functions (declaration, expression, arrow functions)

2. **Scope and Closures**

3. **Objects and Object-Oriented Programming**
   - Object creation and manipulation
   - Prototypes and inheritance
   - Classes (ES6+)

4. **Arrays and Array Methods**
   - map, filter, reduce, forEach, etc.

5. **Asynchronous JavaScript**
   - Callbacks
   - Promises
   - Async/Await

6. **ES6+ Features**
   - let and const
   - Template literals
   - Destructuring
   - Spread and rest operators
   - Default parameters

7. **DOM Manipulation and Events**

8. **Error Handling**
   - try/catch
   - Error objects

9. **Functional Programming Concepts**

10. **JavaScript Design Patterns**

11. **Module Systems**
    - CommonJS
    - ES Modules

12. **this keyword and its behavior**

13. **Event Loop and JavaScript Runtime**

14. **Higher-Order Functions**

15. **Hoisting**

16. **Debugging JavaScript**

17. **Performance Optimization**

18. **Web APIs**
    - Fetch API
    - LocalStorage/SessionStorage

19. **AJAX and HTTP requests**

20. **Strict Mode**

21. **Regular Expressions**

22. **JavaScript Best Practices and Clean Code**

23. **Testing in JavaScript**

24. **Basic algorithms and problem-solving**

## Testing

To run tests (once implemented):

``` batch
npm test
```

## Resume

### 1. JavaScript Fundamentals

#### Variables and Data Types

JavaScript has three ways to declare variables:

- `var`: Function-scoped or globally-scoped variable (avoid using in modern JavaScript)
- `let`: Block-scoped variable that can be reassigned
- `const`: Block-scoped variable that cannot be reassigned

Data types in JavaScript:

- Primitive types: number, string, boolean, null, undefined, symbol, bigint
- Object type: object (including arrays and functions)

Example:

```javascript
let age = 25; // number
const name = "John"; // string
let isStudent = true; // boolean
const fruits = ["apple", "banana", "orange"]; // array (object)
const person = { name: "Alice", age: 30 }; // object
```

#### Operators and Expressions

JavaScript supports various operators:

- Arithmetic: `+`, `-`, `*`, `/`, `%`, `**`
- Comparison: `==`, `===`, `!=`, `!==`, `>`, `<`, `>=`, `<=`
- Logical: `&&`, `||`, `!`
- Assignment: `=`, `+=`, `-=`, `*=`, `/=`
- Ternary: `condition ? expr1 : expr2`

Example:

```javascript
let x = 5;
let y = 3;
let sum = x + y; // 8
let isGreater = x > y; // true
let result = isGreater ? "x is greater" : "y is greater or equal";
```

#### Control Structures

Control structures in JavaScript include:

- if/else statements
- switch statements
- for loops
- while loops
- do...while loops

Example:

```javascript
// if/else statement
if (age >= 18) {
    console.log("You can vote");
} else {
    console.log("You cannot vote yet");
}

// for loop
for (let i = 0; i < 5; i++) {
    console.log(i);
}

// while loop
let count = 0;
while (count < 3) {
    console.log(count);
    count++;
}
```

#### Functions

JavaScript supports various function types:

- Function declarations
- Function expressions
- Arrow functions

Example:

```javascript
// Function declaration
function greet(name) {
    return `Hello, ${name}!`;
}

// Function expression
const multiply = function(a, b) {
    return a * b;
};

// Arrow function
const square = (x) => x * x;

console.log(greet("Alice")); // "Hello, Alice!"
console.log(multiply(4, 5)); // 20
console.log(square(3)); // 9
```

### 2. Scope and Closures

#### Scope

Scope determines the accessibility of variables and functions in JavaScript.

- Global scope: Variables declared outside any function
- Function scope: Variables declared inside a function
- Block scope: Variables declared inside a block (introduced with `let` and `const`)

Example:

```javascript
let globalVar = "I'm global";

function exampleFunction() {
    let functionVar = "I'm function-scoped";
    if (true) {
        let blockVar = "I'm block-scoped";
        console.log(globalVar); // Accessible
        console.log(functionVar); // Accessible
        console.log(blockVar); // Accessible
    }
    console.log(blockVar); // Error: blockVar is not defined
}

console.log(functionVar); // Error: functionVar is not defined
```

#### Closures

A closure is a function that has access to variables in its outer (enclosing) lexical scope, even after the outer function has returned.

Example:

```javascript
function outerFunction(x) {
    let y = 10;
    return function innerFunction(z) {
        return x + y + z;
    };
}

const closure = outerFunction(5);
console.log(closure(3)); // 18 (5 + 10 + 3)
```

### 3. Objects and Object-Oriented Programming

#### Object Creation and Manipulation

Objects in JavaScript are collections of key-value pairs.

Example:

```javascript
// Object literal
const person = {
    name: "John",
    age: 30,
    greet: function() {
        console.log(`Hello, my name is ${this.name}`);
    }
};

// Accessing and modifying properties
console.log(person.name); // "John"
person.age = 31;
person.occupation = "Developer"; // Adding a new property

// Object.create()
const animal = {
    makeSound: function() {
        console.log("Some generic animal sound");
    }
};

const dog = Object.create(animal);
dog.bark = function() {
    console.log("Woof!");
};
```

#### Prototypes and Inheritance

JavaScript uses prototypal inheritance.

Example:

```javascript
function Animal(name) {
    this.name = name;
}

Animal.prototype.makeSound = function() {
    console.log("Some generic animal sound");
};

function Dog(name) {
    Animal.call(this, name);
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.bark = function() {
    console.log("Woof!");
};

const myDog = new Dog("Buddy");
myDog.makeSound(); // "Some generic animal sound"
myDog.bark(); // "Woof!"
```

#### Classes (ES6+)

ES6 introduced a more familiar syntax for creating objects and implementing inheritance.

Example:

```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }

    makeSound() {
        console.log("Some generic animal sound");
    }
}

class Dog extends Animal {
    constructor(name) {
        super(name);
    }

    bark() {
        console.log("Woof!");
    }
}

const myDog = new Dog("Buddy");
myDog.makeSound(); // "Some generic animal sound"
myDog.bark(); // "Woof!"
```

### 4. Arrays and Array Methods

Arrays in JavaScript are objects used to store multiple values in a single variable.

Example:

```javascript
const fruits = ["apple", "banana", "orange"];

// Accessing elements
console.log(fruits[0]); // "apple"

// Adding elements
fruits.push("grape");
fruits.unshift("mango");

// Removing elements
const lastFruit = fruits.pop();
const firstFruit = fruits.shift();
```

#### Array Methods

JavaScript provides many useful methods for working with arrays:

- `map()`: Creates a new array with the results of calling a function for every array element
- `filter()`: Creates a new array with all elements that pass the test implemented by the provided function
- `reduce()`: Executes a reducer function on each element of the array, resulting in a single output value
- `forEach()`: Executes a provided function once for each array element

Example:

```javascript
const numbers = [1, 2, 3, 4, 5];

// map
const doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]

// filter
const evens = numbers.filter(num => num % 2 === 0);
console.log(evens); // [2, 4]

// reduce
const sum = numbers.reduce((acc, curr) => acc + curr, 0);
console.log(sum); // 15

// forEach
numbers.forEach(num => console.log(num));
```

### 5. Asynchronous JavaScript

#### Callbacks

Callbacks are functions passed as arguments to other functions, to be executed once an asynchronous operation has completed.

Example:

```javascript
function fetchData(callback) {
    setTimeout(() => {
        const data = { id: 1, name: "John" };
        callback(data);
    }, 1000);
}

fetchData((result) => {
    console.log(result); // { id: 1, name: "John" }
});
```

#### Promises

Promises represent the eventual completion or failure of an asynchronous operation and its resulting value.

Example:

```javascript
function fetchData() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const data = { id: 1, name: "John" };
            resolve(data);
            // In case of an error: reject(new Error("Failed to fetch data"));
        }, 1000);
    });
}

fetchData()
    .then(result => console.log(result))
    .catch(error => console.error(error));
```

#### Async/Await

Async/await is syntactic sugar built on top of promises, making asynchronous code look and behave more like synchronous code.

Example:

```javascript
async function fetchUserData() {
    try {
        const response = await fetch('https://api.example.com/user');
        const userData = await response.json();
        console.log(userData);
    } catch (error) {
        console.error("Failed to fetch user data:", error);
    }
}

fetchUserData();
```

This async/await example assumes a browser environment or a runtime with `fetch` available. In a Node.js environment, you would typically use a library like `node-fetch` or `axios` for HTTP requests.

Certainly! Here's a detailed resume section for the next five JavaScript concepts in README.md format with examples:

### 6. ES6+ Features

ES6 (ECMAScript 2015) and later versions introduced several new features to JavaScript, enhancing its capabilities and making code more readable and expressive.

#### let and const

`let` and `const` provide block-scoped variable declarations, unlike `var` which is function-scoped.

Example:

```javascript
// let allows reassignment
let count = 1;
count = 2; // Valid

// const creates a read-only reference
const PI = 3.14159;
PI = 3; // Error: Assignment to a constant variable

// Block scoping
if (true) {
    let blockScoped = 'only available in this block';
    var functionScoped = 'available throughout the function';
}
console.log(blockScoped); // ReferenceError
console.log(functionScoped); // Works fine
```

#### Template Literals

Template literals allow for easier string interpolation and multiline strings.

Example:

```javascript
const name = 'Alice';
const greeting = `Hello, ${name}!
Welcome to our website.`;

console.log(greeting);
// Output:
// Hello, Alice!
// Welcome to our website.
```

#### Destructuring

Destructuring allows you to extract values from arrays or properties from objects into distinct variables.

Example:

```javascript
// Array destructuring
const [first, second, ...rest] = [1, 2, 3, 4, 5];
console.log(first); // 1
console.log(second); // 2
console.log(rest); // [3, 4, 5]

// Object destructuring
const person = { name: 'John', age: 30, city: 'New York' };
const { name, age } = person;
console.log(name); // 'John'
console.log(age); // 30
```

#### Spread and Rest Operators

The spread operator (...) allows an iterable to be expanded in places where zero or more arguments or elements are expected. The rest operator collects multiple elements and condenses them into a single array.

Example:

```javascript
// Spread operator
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // [1, 2, 3, 4, 5]

// Rest operator
function sum(...numbers) {
    return numbers.reduce((acc, curr) => acc + curr, 0);
}
console.log(sum(1, 2, 3, 4)); // 10
```

#### Default Parameters

Default parameters allow you to set default values for function parameters.

Example:

```javascript
function greet(name = 'Guest') {
    console.log(`Hello, ${name}!`);
}

greet(); // "Hello, Guest!"
greet('Alice'); // "Hello, Alice!"
```

### 7. DOM Manipulation and Events

The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the structure of a document as a tree-like hierarchy.

#### DOM Manipulation

Example:

```javascript
// Creating a new element
const newParagraph = document.createElement('p');
newParagraph.textContent = 'This is a new paragraph.';

// Appending to the DOM
document.body.appendChild(newParagraph);

// Modifying existing elements
const heading = document.querySelector('h1');
heading.style.color = 'blue';

// Removing elements
const oldParagraph = document.querySelector('#old-paragraph');
oldParagraph.remove();
```

#### Event Handling

Example:

```javascript
// Adding an event listener
const button = document.querySelector('#myButton');
button.addEventListener('click', function(event) {
    console.log('Button clicked!');
    event.preventDefault(); // Prevent default behavior
});

// Event delegation
document.querySelector('#parent-list').addEventListener('click', function(event) {
    if (event.target.tagName === 'LI') {
        console.log('List item clicked:', event.target.textContent);
    }
});
```

### 8. Error Handling

Error handling in JavaScript is crucial for managing and responding to runtime errors effectively.

#### try/catch

The `try/catch` statement marks a block of statements to try and specifies a response should an exception be thrown.

Example:

```javascript
try {
    // Code that may throw an error
    const result = someUndefinedVariable + 5;
} catch (error) {
    console.error('An error occurred:', error.message);
} finally {
    console.log('This will always execute');
}
```

#### Error Objects

JavaScript has built-in error objects that can be thrown or created.

Example:

```javascript
// Throwing a custom error
function divide(a, b) {
    if (b === 0) {
        throw new Error('Division by zero is not allowed');
    }
    return a / b;
}

try {
    console.log(divide(10, 0));
} catch (error) {
    console.error(error.name + ': ' + error.message);
}

// Creating custom error types
class ValidationError extends Error {
    constructor(message) {
        super(message);
        this.name = 'ValidationError';
    }
}

try {
    throw new ValidationError('Invalid input');
} catch (error) {
    if (error instanceof ValidationError) {
        console.error('Validation Error:', error.message);
    } else {
        console.error('Unknown Error:', error);
    }
}
```

### 9. Functional Programming Concepts

Functional programming is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids changing state and mutable data.

#### Pure Functions

Pure functions always produce the same output for the same input and have no side effects.

Example:

```javascript
// Pure function
function add(a, b) {
    return a + b;
}

// Impure function (has side effect)
let total = 0;
function addToTotal(value) {
    total += value;
}
```

#### Higher-Order Functions

Higher-order functions are functions that can take other functions as arguments or return them.

Example:

```javascript
function multiplyBy(factor) {
    return function(number) {
        return number * factor;
    }
}

const double = multiplyBy(2);
console.log(double(5)); // 10
```

#### Immutability

Immutability involves not changing data after it's created.

Example:

```javascript
// Mutable approach
const mutableArray = [1, 2, 3];
mutableArray.push(4); // Modifies the original array

// Immutable approach
const immutableArray = [1, 2, 3];
const newArray = [...immutableArray, 4]; // Creates a new array
```

### 10. JavaScript Design Patterns

Design patterns are reusable solutions to commonly occurring problems in software design.

#### Module Pattern

The Module pattern is used to create private and public encapsulation of methods and variables.

Example:

```javascript
const Calculator = (function() {
    let result = 0;
    
    return {
        add: function(x) {
            result += x;
        },
        subtract: function(x) {
            result -= x;
        },
        getResult: function() {
            return result;
        }
    };
})();

Calculator.add(5);
Calculator.subtract(2);
console.log(Calculator.getResult()); // 3
```

#### Singleton Pattern

The Singleton pattern ensures a class has only one instance and provides a global point of access to it.

Example:

```javascript
const Singleton = (function() {
    let instance;

    function createInstance() {
        const object = new Object("I am the instance");
        return object;
    }

    return {
        getInstance: function() {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();

const instance1 = Singleton.getInstance();
const instance2 = Singleton.getInstance();
console.log(instance1 === instance2); // true
```

#### Observer Pattern

The Observer pattern defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.

Example:

```javascript
class Subject {
    constructor() {
        this.observers = [];
    }

    subscribe(observer) {
        this.observers.push(observer);
    }

    unsubscribe(observer) {
        this.observers = this.observers.filter(obs => obs !== observer);
    }

    notify(data) {
        this.observers.forEach(observer => observer.update(data));
    }
}

class Observer {
    update(data) {
        console.log('Received update:', data);
    }
}

const subject = new Subject();
const observer1 = new Observer();
const observer2 = new Observer();

subject.subscribe(observer1);
subject.subscribe(observer2);

subject.notify('Hello Observers!');
```

These design patterns demonstrate different ways to structure your JavaScript code for better organization, maintainability, and reusability.

### 11. Module Systems

Module systems in JavaScript allow you to organize code into separate files and manage dependencies.

#### CommonJS

CommonJS is the module system used in Node.js.

Example:

```javascript
// math.js
function add(a, b) {
    return a + b;
}

function subtract(a, b) {
    return a - b;
}

module.exports = {
    add: add,
    subtract: subtract
};

// main.js
const math = require('./math');
console.log(math.add(5, 3)); // 8
console.log(math.subtract(10, 4)); // 6
```

#### ES Modules

ES Modules is the standard module system for JavaScript in the browser.

Example:

```javascript
// math.js
export function add(a, b) {
    return a + b;
}

export function subtract(a, b) {
    return a - b;
}

// main.js
import { add, subtract } from './math.js';
console.log(add(5, 3)); // 8
console.log(subtract(10, 4)); // 6
```

### 12. this keyword and its behavior

The `this` keyword in JavaScript refers to the object that is executing the current function. Its value can change depending on how a function is called.

Example:

```javascript
// Global context
console.log(this === window); // true (in a browser)

// Object method
const obj = {
    name: 'John',
    greet: function() {
        console.log(`Hello, ${this.name}!`);
    }
};
obj.greet(); // "Hello, John!"

// Constructor function
function Person(name) {
    this.name = name;
}
const person = new Person('Alice');
console.log(person.name); // "Alice"

// Arrow functions
const arrowObj = {
    name: 'Bob',
    greet: () => {
        console.log(`Hello, ${this.name}!`);
    }
};
arrowObj.greet(); // "Hello, undefined!" (this refers to global/window object)

// Explicit binding
function introduce() {
    console.log(`I am ${this.name}`);
}
const person1 = { name: 'Charlie' };
const person2 = { name: 'David' };
introduce.call(person1); // "I am Charlie"
introduce.apply(person2); // "I am David"
```

### 13. Event Loop and JavaScript Runtime

The event loop is a fundamental concept in JavaScript that allows for non-blocking I/O operations despite JavaScript being single-threaded.

Example:

```javascript
console.log('Start');

setTimeout(() => {
    console.log('Timeout 1');
}, 0);

Promise.resolve().then(() => {
    console.log('Promise 1');
});

setTimeout(() => {
    console.log('Timeout 2');
}, 0);

Promise.resolve().then(() => {
    console.log('Promise 2');
});

console.log('End');

// Output:
// Start
// End
// Promise 1
// Promise 2
// Timeout 1
// Timeout 2
```

Explanation:

1. Synchronous code runs first ('Start' and 'End').
2. Microtasks (Promises) are processed next.
3. Macrotasks (setTimeout callbacks) are processed last.

### 14. Higher-Order Functions

Higher-order functions are functions that can take other functions as arguments or return them.

Example:

```javascript
// Function that takes a function as an argument
function operateOnArray(arr, operation) {
    return arr.map(operation);
}

const numbers = [1, 2, 3, 4, 5];

const doubled = operateOnArray(numbers, num => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]

const squared = operateOnArray(numbers, num => num ** 2);
console.log(squared); // [1, 4, 9, 16, 25]

// Function that returns a function
function multiplyBy(factor) {
    return function(number) {
        return number * factor;
    };
}

const triple = multiplyBy(3);
console.log(triple(4)); // 12
console.log(triple(5)); // 15
```

### 15. Hoisting

Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their respective scopes during the compilation phase, before the code is executed.

Example:

```javascript
// Variable hoisting
console.log(x); // undefined
var x = 5;

// The above is interpreted as:
// var x;
// console.log(x);
// x = 5;

// Function declaration hoisting
sayHello(); // "Hello!"

function sayHello() {
    console.log("Hello!");
}

// Function expressions are not hoisted
try {
    sayGoodbye(); // Throws "TypeError: sayGoodbye is not a function"
} catch (error) {
    console.error(error);
}

var sayGoodbye = function() {
    console.log("Goodbye!");
};

// let and const are hoisted but not initialized (Temporal Dead Zone)
console.log(y); // Throws "ReferenceError: Cannot access 'y' before initialization"
let y = 10;
```

Important notes about hoisting:

1. Only declarations are hoisted, not initializations.
2. Function declarations are hoisted entirely.
3. `let` and `const` declarations are hoisted but not initialized, resulting in a Temporal Dead Zone.
4. It's generally considered best practice to declare variables at the top of their scope to avoid confusion.

### 16. Debugging JavaScript

Debugging is an essential skill for JavaScript developers. There are various tools and techniques available for debugging JavaScript code.

#### Console Methods

The `console` object provides several methods for debugging:

```javascript
console.log('Basic logging');
console.error('Error message');
console.warn('Warning message');
console.table([{ name: 'John', age: 30 }, { name: 'Jane', age: 25 }]);

// Grouping console messages
console.group('User Details');
console.log('Name: John Doe');
console.log('Age: 30');
console.groupEnd();

// Timing operations
console.time('Loop time');
for(let i = 0; i < 1000000; i++) {}
console.timeEnd('Loop time');
```

#### Breakpoints

Using the browser's developer tools, you can set breakpoints in your code:

```javascript
function calculateTotal(price, quantity) {
    let subtotal = price * quantity;
    let tax = subtotal * 0.08;  // Set a breakpoint on this line
    return subtotal + tax;
}

let total = calculateTotal(10, 5);
console.log(total);
```

#### Debug with debugger keyword

You can use the `debugger` keyword to pause execution:

```javascript
function complexCalculation(x, y) {
    debugger;  // Execution will pause here when Dev Tools are open
    let result = x * y / (x - y);
    return result;
}

complexCalculation(10, 5);
```

### 17. Performance Optimization

Optimizing JavaScript performance is crucial for creating efficient web applications.

#### Minimize DOM Manipulation

```javascript
// Inefficient
for (let i = 0; i < 1000; i++) {
    document.body.innerHTML += '<div>' + i + '</div>';
}

// More efficient
let html = '';
for (let i = 0; i < 1000; i++) {
    html += '<div>' + i + '</div>';
}
document.body.innerHTML = html;
```

#### Use Event Delegation

```javascript
// Instead of adding event listeners to each button
document.getElementById('button-container').addEventListener('click', function(e) {
    if (e.target.className === 'button') {
        console.log('Button clicked:', e.target.textContent);
    }
});
```

#### Debounce Function Calls

```javascript
function debounce(func, wait) {
    let timeout;
    return function executedFunction(...args) {
        const later = () => {
            clearTimeout(timeout);
            func(...args);
        };
        clearTimeout(timeout);
        timeout = setTimeout(later, wait);
    };
}

const debouncedSearch = debounce(() => {
    // Perform search operation
    console.log('Searching...');
}, 300);

// In an input event listener
input.addEventListener('input', debouncedSearch);
```

### 18. Web APIs

#### Fetch API

The Fetch API provides an interface for fetching resources (including across the network).

```javascript
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));

// Using async/await
async function fetchData() {
    try {
        const response = await fetch('https://api.example.com/data');
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('Error:', error);
    }
}
```

#### LocalStorage/SessionStorage

Web Storage API provides mechanisms for storing key-value pairs in a web browser.

```javascript
// LocalStorage
localStorage.setItem('username', 'John');
console.log(localStorage.getItem('username')); // 'John'
localStorage.removeItem('username');

// SessionStorage
sessionStorage.setItem('tempData', 'Some temporary data');
console.log(sessionStorage.getItem('tempData')); // 'Some temporary data'
sessionStorage.clear(); // Clears all data
```

### 19. AJAX and HTTP Requests

AJAX (Asynchronous JavaScript and XML) allows web pages to be updated asynchronously by exchanging data with a server behind the scenes.

```javascript
// Using XMLHttpRequest (older method)
var xhr = new XMLHttpRequest();
xhr.onreadystatechange = function() {
    if (xhr.readyState === XMLHttpRequest.DONE) {
        if (xhr.status === 200) {
            console.log(xhr.responseText);
        } else {
            console.error('Request failed');
        }
    }
};
xhr.open('GET', 'https://api.example.com/data', true);
xhr.send();

// Using Fetch API (modern method)
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));

// POST request with Fetch API
fetch('https://api.example.com/submit', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
    },
    body: JSON.stringify({ username: 'John', password: 'password123' }),
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

### 20. Strict Mode

Strict mode is a way to opt in to a restricted variant of JavaScript. It eliminates some JavaScript silent errors by changing them to throw errors.

To enable strict mode, add `"use strict";` at the beginning of a script or a function.

```javascript
"use strict";

// Variables must be declared
x = 3.14; // This will cause an error

// Deleting a variable is not allowed
let y = 5;
delete y; // This will cause an error

// Writing to a read-only global is not allowed
var undefined = 5; // This will cause an error

// Duplicate parameter names are not allowed
function sum(a, a, c) { // This will cause an error
    return a + a + c;
}

// 'this' is undefined in functions in strict mode unless set explicitly
function showThis() {
    console.log(this); // 'undefined' in strict mode, 'window' in non-strict mode
}
showThis();

// The 'with' statement is not allowed
with (Math) { // This will cause an error
    x = cos(2);
}
```

Benefits of strict mode:

1. Prevents accidental globals
2. Throws error on invalid usage of delete
3. Prevents duplicate property names or parameter values
4. Makes eval() safer
5. Throws errors on invalid use of `this`

It's generally a good practice to use strict mode in your JavaScript files or functions to catch common coding bloopers and prevent the use of certain error-prone features.

### 21. Regular Expressions

Regular expressions (regex) are patterns used to match character combinations in strings. They are incredibly useful for tasks like validation, searching, and replacing text.

#### Basic Syntax

```javascript
// Creating a regex
let pattern = /abc/;
let regexObject = new RegExp('abc');

// Testing a string
console.log(pattern.test('abcdef')); // true
console.log(pattern.test('defabc')); // true
console.log(pattern.test('def')); // false

// Matching
let result = 'abcdef'.match(/abc/);
console.log(result[0]); // 'abc'
```

#### Common Patterns

```javascript
// Any digit: \d
let hasNumber = /\d/.test('abc123'); // true

// Any word character (letter, number, underscore): \w
let hasWordChar = /\w/.test('abc_123'); // true

// Whitespace: \s
let hasWhitespace = /\s/.test('abc 123'); // true

// Beginning of string: ^
let startsWithAbc = /^abc/.test('abcdef'); // true

// End of string: $
let endsWithXyz = /xyz$/.test('defxyz'); // true

// Zero or more occurrences: *
let zeroOrMore = /ab*c/.test('ac'); // true

// One or more occurrences: +
let oneOrMore = /ab+c/.test('abc'); // true

// Optional character: ?
let optional = /colou?r/.test('color'); // true
```

#### Practical Examples

```javascript
// Email validation
let emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
console.log(emailPattern.test('user@example.com')); // true
console.log(emailPattern.test('invalid-email')); // false

// Phone number format (US)
let phonePattern = /^\(\d{3}\)\s\d{3}-\d{4}$/;
console.log(phonePattern.test('(123) 456-7890')); // true
console.log(phonePattern.test('123-456-7890')); // false

// Password strength (at least 8 characters, 1 uppercase, 1 lowercase, 1 number)
let passwordPattern = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)[a-zA-Z\d]{8,}$/;
console.log(passwordPattern.test('Passw0rd')); // true
console.log(passwordPattern.test('weakpass')); // false
```

### 22. JavaScript Best Practices and Clean Code

Writing clean, maintainable JavaScript code is crucial for long-term project success. Here are some best practices:

#### Use Meaningful Names

```javascript
// Bad
const x = 5;
const arr = ['John', 'Jane', 'Bob'];

// Good
const maxAttempts = 5;
const userNames = ['John', 'Jane', 'Bob'];
```

#### Use const and let, Avoid var

```javascript
// Bad
var count = 1;
var name = 'John';

// Good
const name = 'John';
let count = 1;
```

#### Use Arrow Functions for Short Functions

```javascript
// Less readable
const multiply = function(a, b) {
    return a * b;
};

// More concise
const multiply = (a, b) => a * b;
```

#### Use Template Literals for String Interpolation

```javascript
// Less readable
const greeting = 'Hello, ' + name + '! You are ' + age + ' years old.';

// More readable
const greeting = `Hello, ${name}! You are ${age} years old.`;
```

#### Use Destructuring

```javascript
// Without destructuring
const firstName = user.firstName;
const lastName = user.lastName;

// With destructuring
const { firstName, lastName } = user;
```

#### Use Shorthand Object Properties

```javascript
// Less concise
const user = {
    name: name,
    age: age,
    city: city
};

// More concise
const user = { name, age, city };
```

#### Use Async/Await for Asynchronous Code

```javascript
// Using Promises
fetchData()
    .then(data => processData(data))
    .then(result => console.log(result))
    .catch(error => console.error(error));

// Using Async/Await
async function handleData() {
    try {
        const data = await fetchData();
        const result = await processData(data);
        console.log(result);
    } catch (error) {
        console.error(error);
    }
}
```

#### Write Self-Documenting Code

```javascript
// Less clear
if (age >= 18) {
    // Allow access
}

// More clear
const isAdult = age >= 18;
if (isAdult) {
    allowAccess();
}
```

### 23. Testing in JavaScript

Testing is crucial for ensuring code quality and preventing regressions. Here are some common testing approaches in JavaScript:

#### Unit Testing with Jest

Jest is a popular testing framework for JavaScript.

```javascript
// math.js
export function add(a, b) {
    return a + b;
}

// math.test.js
import { add } from './math';

test('adds 1 + 2 to equal 3', () => {
    expect(add(1, 2)).toBe(3);
});

test('adds -1 + 1 to equal 0', () => {
    expect(add(-1, 1)).toBe(0);
});
```

#### Asynchronous Testing

```javascript
// api.js
export function fetchUser(id) {
    return fetch(`https://api.example.com/users/${id}`)
        .then(response => response.json());
}

// api.test.js
import { fetchUser } from './api';

test('fetchUser returns user data', async () => {
    const user = await fetchUser(1);
    expect(user).toHaveProperty('name');
    expect(user).toHaveProperty('email');
});
```

#### Mocking

```javascript
// database.js
export function saveUser(user) {
    // Actual database call
}

// userService.js
import { saveUser } from './database';

export function createUser(userData) {
    const user = { ...userData, createdAt: new Date() };
    return saveUser(user);
}

// userService.test.js
import { createUser } from './userService';
import { saveUser } from './database';

jest.mock('./database');

test('createUser calls saveUser with correct data', () => {
    const userData = { name: 'John', email: 'john@example.com' };
    createUser(userData);
    expect(saveUser).toHaveBeenCalledWith(expect.objectContaining(userData));
});
```

#### Test Coverage

Jest provides built-in coverage reporting:

```bash
jest --coverage
```

This will generate a coverage report, showing which parts of your code are covered by tests.

### 24. Basic Algorithms and Problem-Solving

Problem-solving is a crucial skill for developers. Here are some basic algorithms and problem-solving techniques:

#### Sorting Algorithms

##### Bubble Sort

```javascript
function bubbleSort(arr) {
    const n = arr.length;
    for (let i = 0; i < n - 1; i++) {
        for (let j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Swap elements
                [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
            }
        }
    }
    return arr;
}

console.log(bubbleSort([64, 34, 25, 12, 22, 11, 90]));
```

#### Searching Algorithms

##### Binary Search

```javascript
function binarySearch(arr, target) {
    let left = 0;
    let right = arr.length - 1;

    while (left <= right) {
        const mid = Math.floor((left + right) / 2);
        if (arr[mid] === target) return mid;
        if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }

    return -1; // Target not found
}

console.log(binarySearch([1, 3, 5, 7, 9], 5)); // 2
console.log(binarySearch([1, 3, 5, 7, 9], 6)); // -1
```

#### Problem-Solving Techniques

##### Two-Pointer Technique

```javascript
// Find a pair in a sorted array that sums to a target
function findPair(arr, target) {
    let left = 0;
    let right = arr.length - 1;

    while (left < right) {
        const sum = arr[left] + arr[right];
        if (sum === target) return [arr[left], arr[right]];
        if (sum < target) left++;
        else right--;
    }

    return null; // No pair found
}

console.log(findPair([1, 2, 3, 4, 5], 7)); // [2, 5]
console.log(findPair([1, 2, 3, 4, 5], 10)); // null
```

##### Dynamic Programming

```javascript
// Fibonacci sequence using dynamic programming
function fibonacci(n) {
    if (n <= 1) return n;

    let fib = [0, 1];
    for (let i = 2; i <= n; i++) {
        fib[i] = fib[i-1] + fib[i-2];
    }

    return fib[n];
}

console.log(fibonacci(10)); // 55
```

##### Recursion

```javascript
// Factorial using recursion
function factorial(n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}

console.log(factorial(5)); // 120
```

These examples demonstrate basic algorithms and problem-solving techniques. When approaching a new problem, it's important to:

1. Understand the problem thoroughly
2. Break it down into smaller, manageable parts
3. Consider multiple approaches
4. Implement the solution step by step
5. Test with various inputs, including edge cases
6. Optimize for time and space complexity if necessary

Regular practice with algorithmic problems can significantly improve your problem-solving skills and prepare you for technical interviews.

## Linting

To lint your code:

``` batch
npm run lint
```

## Additional Information

- This project uses TypeScript, which is a typed superset of JavaScript.
- Express is used as the web application framework.
- ESLint is used for linting with TypeScript support.

For more information on Express, visit: <https://expressjs.com/>

For more information on TypeScript, visit: <https://www.typescriptlang.org/>

If you have any questions or need further assistance, please open an issue in the GitHub repository.
