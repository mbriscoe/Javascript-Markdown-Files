# JavaScript Truthy and Falsy Values

Understanding how JavaScript evaluates values as true or false is essential for writing effective code. In JavaScript, every value is either "truthy" or "falsy" when evaluated in a Boolean context (such as an `if` statement).

## Falsy Values

A falsy value is a value that translates to `false` when evaluated in a Boolean context. There are only **seven** falsy values in JavaScript:

1. `false` (the Boolean value false)
2. `0` (the Number zero)
3. `-0` (negative zero)
4. `""` (empty string)
5. `null`
6. `undefined`
7. `NaN` (Not-a-Number)

Any value other than these is considered **truthy**.

## Truthy Values

A truthy value is any value that is not falsy. This includes:

-   Non-empty strings (e.g., `"hello"`)
-   Any number except `0`, `-0`, or `NaN` (e.g., `42`, `-7`)
-   Objects (including arrays and functions)
-   `true`

## Examples

```javascript
if ('hello') {
    console.log('This is truthy!'); // This will run
}

if ('') {
    console.log('This is falsy!'); // This will NOT run
}

if (0) {
    console.log('Zero is falsy!'); // This will NOT run
}

if ([]) {
    console.log('An empty array is truthy!'); // This will run
}
```

## Why Does This Matter?

Understanding truthy and falsy values helps you:

-   Write concise conditional statements
-   Avoid bugs caused by unexpected type coercion
-   Validate user input effectively

## Common Pitfalls

-   **Empty arrays and objects are truthy:**
    ```javascript
    if ({}) {
        /* runs */
    }
    if ([]) {
        /* runs */
    }
    ```
-   **String "false" is truthy:**
    ```javascript
    if ('false') {
        /* runs */
    }
    ```

## Checking for Truthy/Falsy

You can use the Boolean function to explicitly convert a value:

```javascript
Boolean(''); // false
Boolean('hello'); // true
Boolean(0); // false
Boolean({}); // true
```

Or use double NOT (`!!`) to coerce a value to true or false:

```javascript
!!''; // false
!!'hello'; // true
```

## Summary

-   There are only seven falsy values in JavaScript.
-   Everything else is truthy.
-   Use this knowledge to write better conditionals and avoid bugs!
