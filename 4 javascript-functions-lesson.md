# JavaScript Functions Lesson

## Introduction

Functions are one of the core building blocks in JavaScript. They allow you to encapsulate code for reuse, organization, and abstraction. In this lesson, you'll learn about function declaration, invocation, parameters, return values, scope, and advanced topics like arrow functions and callbacks.

## 1. Function Declaration

A function can be declared using the `function` keyword.

```javascript
function greet() {
    console.log('Hello, world!');
}

greet(); // Output: Hello, world!
```

## 2. Function Parameters and Arguments

Functions can accept parameters, which act as placeholders for values.

```javascript
function add(a, b) {
    return a + b;
}

console.log(add(2, 3)); // Output: 5
```

## 3. Return Values

Functions can return values using the `return` statement.

```javascript
function square(x) {
    return x * x;
}

let result = square(4);
console.log(result); // Output: 16
```

## 4. Function Expressions

Functions can be assigned to variables.

```javascript
const multiply = function (a, b) {
    return a * b;
};

console.log(multiply(3, 4)); // Output: 12
```

## 5. Arrow Functions

Arrow functions provide a shorter syntax.

```javascript
const divide = (a, b) => a / b;
console.log(divide(10, 2)); // Output: 5
```

## 6. Default Parameters

You can set default values for parameters.

```javascript
function greet(name = 'Guest') {
    console.log('Hello, ' + name);
}

greet(); // Output: Hello, Guest
greet('Mark'); // Output: Hello, Mark
```

## 7. Rest Parameters

Rest parameters allow you to pass an indefinite number of arguments.

```javascript
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3, 4)); // Output: 10
```

## 8. Scope

Variables declared inside a function are local to that function.

```javascript
function showScope() {
    let localVar = 'I am local';
    console.log(localVar);
}

showScope(); // Output: I am local
// console.log(localVar); // Error: localVar is not defined
```

## 9. Callback Functions

Functions can be passed as arguments to other functions.

```javascript
function processUserInput(callback) {
    const name = 'Alice';
    callback(name);
}

processUserInput(function (name) {
    console.log('Hello, ' + name);
}); // Output: Hello, Alice
```

## 10. Anonymous Functions

Functions without a name are called anonymous functions.

```javascript
setTimeout(function () {
    console.log('Executed after 1 second');
}, 1000);
```

## 11. Immediately Invoked Function Expressions (IIFE)

IIFEs run as soon as they are defined.

```javascript
(function () {
    console.log('IIFE executed!');
})();
```

## 12. Practical Example: Filtering an Array

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter(function (num) {
    return num % 2 === 0;
});
console.log(evenNumbers); // Output: [2, 4, 6]
```

## Summary

# JavaScript Functions: A Comprehensive Lesson

## Table of Contents

1. Introduction
2. What is a Function?
3. Function Declaration
4. Function Invocation
5. Parameters and Arguments
6. Return Values
7. Function Expressions
8. Arrow Functions
9. Default Parameters
10. Rest Parameters
11. The `arguments` Object
12. Scope and Closures
13. Function Hoisting
14. Anonymous vs. Named Functions
15. Callback Functions
16. Pure vs. Impure Functions
17. Recursion
18. Immediately Invoked Function Expressions (IIFE)
19. Practical Examples
20. Best Practices
21. Common Pitfalls
22. Exercises
23. References

---

## 1. Introduction

Functions are fundamental building blocks in JavaScript. They allow you to:

-   Encapsulate logic for reuse
-   Organize code into manageable pieces
-   Abstract complexity
-   Enable functional programming patterns

---

## 2. What is a Function?

A function is a block of code designed to perform a particular task. It can take inputs (parameters), process them, and return an output.

**Diagram:**

```
Input (parameters) ---> [ Function ] ---> Output (return value)
```

---

## 3. Function Declaration

Declared using the `function` keyword:

```javascript
function greet() {
    console.log('Hello, world!');
}

greet(); // Output: Hello, world!
```

**Notes:**

-   Function declarations are hoisted (see section 13).
-   Can be called before their definition in code.

---

## 4. Function Invocation

To run a function, use its name followed by parentheses:

```javascript
greet(); // Invokes the greet function
```

You can invoke functions with arguments:

```javascript
function sayHello(name) {
    console.log('Hello, ' + name);
}
sayHello('Mark'); // Output: Hello, Mark
```

---

## 5. Parameters and Arguments

Parameters are variables listed in the function definition. Arguments are values passed to the function.

```javascript
function add(a, b) {
    return a + b;
}
console.log(add(2, 3)); // Output: 5
```

**Edge Cases:**

-   If fewer arguments are passed, missing parameters are `undefined`.
-   Extra arguments are ignored unless handled with rest parameters or `arguments`.

---

## 6. Return Values

Use `return` to send a value back to the caller:

```javascript
function square(x) {
    return x * x;
}
let result = square(4); // result is 16
```

**Notes:**

-   If no `return`, function returns `undefined`.
-   `return` immediately exits the function.

---

## 7. Function Expressions

Functions can be assigned to variables:

```javascript
const multiply = function (a, b) {
    return a * b;
};
console.log(multiply(3, 4)); // Output: 12
```

**Notes:**

-   Function expressions are not hoisted.
-   Can be anonymous or named.

---

## 8. Arrow Functions

Shorter syntax introduced in ES6:

```javascript
const divide = (a, b) => a / b;
console.log(divide(10, 2)); // Output: 5
```

**Features:**

-   No own `this`, `arguments`, or `super`.
-   Cannot be used as constructors.

**Multi-line Arrow Function:**

```javascript
const logNumbers = arr => {
    arr.forEach(num => console.log(num));
};
```

---

## 9. Default Parameters

Set default values for parameters:

```javascript
function greet(name = 'Guest') {
    console.log('Hello, ' + name);
}
greet(); // Output: Hello, Guest
greet('Mark'); // Output: Hello, Mark
```

---

## 10. Rest Parameters

Allows indefinite number of arguments:

```javascript
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3, 4)); // Output: 10
```

---

## 11. The `arguments` Object

All regular functions have access to the `arguments` object (not arrow functions):

```javascript
function showArguments() {
    console.log(arguments);
}
showArguments(1, 'a', true); // Output: [1, 'a', true]
```

---

## 12. Scope and Closures

**Scope:**

-   Variables declared inside a function are local.

```javascript
function showScope() {
    let localVar = 'I am local';
    console.log(localVar);
}
showScope(); // Output: I am local
// console.log(localVar); // Error: localVar is not defined
```

**Closure:**

-   Functions remember variables from their outer scope.

```javascript
function outer() {
    let count = 0;
    function inner() {
        count++;
        return count;
    }
    return inner;
}
const counter = outer();
console.log(counter()); // 1
console.log(counter()); // 2
```

---

## 13. Function Hoisting

Function declarations are hoisted:

```javascript
hoisted(); // Works!
function hoisted() {
    console.log('This function is hoisted');
}
```

Function expressions are NOT hoisted:

```javascript
// notHoisted(); // Error
const notHoisted = function () {
    console.log('Not hoisted');
};
```

---

## 14. Anonymous vs. Named Functions

**Anonymous:**

```javascript
const anon = function () {
    console.log('Anonymous');
};
```

**Named:**

```javascript
const named = function namedFunc() {
    console.log('Named');
};
```

Named functions are useful for debugging (stack traces).

---

## 15. Callback Functions

Functions passed as arguments to other functions:

```javascript
function processUserInput(callback) {
    const name = 'Alice';
    callback(name);
}
processUserInput(function (name) {
    console.log('Hello, ' + name);
}); // Output: Hello, Alice
```

**Common Uses:**

-   Array methods (`map`, `filter`, `reduce`)
-   Event handlers
-   Asynchronous code (setTimeout, AJAX)

---

## 16. Pure vs. Impure Functions

**Pure:**

-   Output depends only on input, no side effects.

```javascript
function pureAdd(a, b) {
    return a + b;
}
```

**Impure:**

-   Modifies external state or relies on it.

```javascript
let total = 0;
function impureAdd(a) {
    total += a;
    return total;
}
```

---

## 17. Recursion

A function calling itself:

```javascript
function factorial(n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}
console.log(factorial(5)); // Output: 120
```

**Notes:**

-   Must have a base case to avoid infinite loop.

---

## 18. Immediately Invoked Function Expressions (IIFE)

Runs as soon as defined:

```javascript
(function () {
    console.log('IIFE executed!');
})();
```

**Use Cases:**

-   Create a private scope
-   Avoid polluting global namespace

---

## 19. Practical Examples

**Filtering an Array:**

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter(function (num) {
    return num % 2 === 0;
});
console.log(evenNumbers); // Output: [2, 4, 6]
```

**Using Arrow Functions with Array Methods:**

```javascript
const doubled = numbers.map(n => n * 2);
console.log(doubled); // Output: [2, 4, 6, 8, 10, 12]
```

**Callback for Asynchronous Code:**

```javascript
setTimeout(() => {
    console.log('Executed after 1 second');
}, 1000);
```

---

## 20. Best Practices

-   Use descriptive names for functions and parameters
-   Keep functions small and focused
-   Prefer pure functions when possible
-   Avoid modifying global state inside functions
-   Use arrow functions for short callbacks
-   Document function purpose and parameters

---

## 21. Common Pitfalls

-   Forgetting to use `return` when needed
-   Using arrow functions when `this` is required
-   Not handling missing or extra arguments
-   Infinite recursion (missing base case)
-   Overusing global variables

---
