# JavaScript Data Types: Detailed Lesson

JavaScript is a dynamically typed language, meaning variables can hold any type of data and types are determined at runtime. Data types are divided into two main categories: primitive and reference types.

---

## 1. Primitive Data Types

Primitive types are immutable and represent a single value. There are seven primitive types:

### a. Number

Represents numeric values, including integers, floating-point numbers, and special values like `Infinity` and `NaN`.

```javascript
let count = 42; // Integer
let temperature = -5.3; // Floating-point
let infinity = Infinity; // Represents infinity
let notANumber = NaN; // Represents "Not a Number", e.g. invalid math
```

**Note:** All numbers in JavaScript (except BigInt) are stored as 64-bit floating-point values.

### b. String

Represents sequences of characters. Strings are immutable.

```javascript
let firstName = 'Alice'; // Double quotes
let lastName = 'Smith'; // Single quotes
let greeting = `Hello, ${firstName} ${lastName}!`; // Template literals allow embedding expressions
```

**Note:** Strings can be concatenated and manipulated with built-in methods like `.length`, `.toUpperCase()`, etc.

### c. Boolean

Represents logical values: `true` or `false`.

```javascript
let isLoggedIn = true;
let hasAccess = false;
```

**Note:** Booleans are often used in conditional statements and comparisons.

### d. Undefined

A variable that has been declared but not assigned a value is `undefined`.

```javascript
let result;
console.log(result); // undefined
```

**Note:** Functions return `undefined` if no return value is specified.

### e. Null

Represents the intentional absence of any object value.

```javascript
let selectedItem = null;
```

**Note:** `null` is often used to reset or clear variables.

### f. Symbol (ES6)

Represents a unique and immutable identifier, often used as object property keys to avoid name collisions.

```javascript
let uniqueId = Symbol('id');
let anotherId = Symbol('id');
console.log(uniqueId === anotherId); // false, each Symbol is unique
```

### g. BigInt (ES2020)

Allows representation of integers larger than the `Number.MAX_SAFE_INTEGER`.

```javascript
let bigNumber = 1234567890123456789012345678901234567890n;
console.log(typeof bigNumber); // "bigint"
```

---

## 2. Reference Data Types

Reference types store collections of values or more complex entities. They are mutable and variables store references (addresses) to the data.

### a. Object

Objects are collections of key-value pairs. Keys are strings (or Symbols), and values can be any type.

```javascript
let person = {
    name: 'Bob',
    age: 25,
    isStudent: true,
};
console.log(person.name); // "Bob"
```

**Note:** Objects can be nested and modified after creation.

### b. Array

Arrays are ordered lists of values, indexed by numbers starting at 0.

```javascript
let colors = ['red', 'green', 'blue'];
console.log(colors[1]); // "green"
colors.push('yellow'); // Adds "yellow" to the end
```

**Note:** Arrays are objects with special methods like `.push()`, `.pop()`, `.length`, etc.

### c. Function

Functions are first-class objects, meaning they can be assigned to variables, passed as arguments, and returned from other functions.

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet('Alice')); // "Hello, Alice!"
```

**Note:** Functions can also be created using arrow syntax: `const add = (a, b) => a + b;`

---

## 3. Type Checking

Use the `typeof` operator to check the type of a variable:

```javascript
console.log(typeof 42); // "number"
console.log(typeof 'hello'); // "string"
console.log(typeof true); // "boolean"
console.log(typeof undefined); // "undefined"
console.log(typeof null); // "object" (historical bug)
console.log(typeof Symbol('id')); // "symbol"
console.log(typeof 123n); // "bigint"
console.log(typeof {}); // "object"
console.log(typeof []); // "object" (arrays are objects)
console.log(typeof function () {}); // "function"
```

---

## 4. Special Notes

-   **Dynamic Typing:** Variables can change type at runtime.
-   **Type Coercion:** JavaScript automatically converts types in certain operations (e.g., `"5" + 1` results in `"51"`).
-   **Null vs Undefined:** `null` is an assigned value, `undefined` means no value assigned.

---
