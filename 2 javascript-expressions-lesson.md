# JavaScript Expressions

An **expression** in JavaScript is any valid unit of code that resolves to a value. Expressions are the building blocks of JavaScript programs and are used everywhere—from assignments to function arguments and conditionals.

## Types of Expressions

### 1. Arithmetic Expressions

These use arithmetic operators to produce numeric values.

```javascript
2 + 3; // 5
10 * 4; // 40
7 / 2; // 3.5
```

### 2. String Expressions

Combining or manipulating strings.

```javascript
'Hello' + ' World'; // "Hello World"
```

### 3. Logical Expressions

Use logical operators to produce Boolean values.

```javascript
true && false; // false
5 > 3 || 2 < 1; // true
```

### 4. Assignment Expressions

Assign a value to a variable.

```javascript
let x = 10;
x += 5; // x is now 15
```

### 5. Function Expressions

Functions can be defined as expressions.

```javascript
const add = function (a, b) {
    return a + b;
};
```

### 6. Conditional (Ternary) Expressions

A shorthand for `if...else`.

```javascript
let result = score > 50 ? 'Pass' : 'Fail';
```

## Expression vs Statement

-   **Expression:** Produces a value (e.g., `2 + 2`)
-   **Statement:** Performs an action (e.g., `if (x > 0) { ... }`)

Often, statements contain expressions.

## Examples in Context

```javascript
let total = 5 * (2 + 3); // 5 * 5 = 25
let greeting = 'Hi, ' + name;
let isAdult = age >= 18;
```

## Why Are Expressions Important?

-   They are used to calculate values
-   They make up the logic of your code
-   Understanding them helps you write more complex programs

## Summary

-   Expressions resolve to values
-   They are used everywhere in JavaScript
-   Mastering expressions is key to writing effective code
