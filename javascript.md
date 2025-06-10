---
title: Collection of JavaScript Interview Questions
author: Jacob Nelson
date: 2024-03-14
tags: [javascript, tutorial, interview]
---

## data types

JavaScript provides eight different data types which are `undefined`, `null`, `boolean`, `string`, `symbol`, `bigint`, `number`, and `object`.

`Number` is a data type in JavaScript which represents numeric data.

### string literal

A string literal, or string, is a series of zero or more characters enclosed in single or double quotes.

`var myName = "your name";`

### what is the data type of null?
`typeof null` is `object`

### difference between `replaceAll()` and `replace()` methods

The main differences between replaceAll() and replace() in JavaScript lie in their behavior and browser support:

**replace():**
- Replaces only the first occurrence of the matched pattern in the string.
- If the g (global) flag is not included, it only replaces the first match.
     
**replaceAll():**
- Replaces all occurrences of the matched pattern in the string.
- This behavior is inherent to the method, and the g flag is not necessary.

| Feature | replace() | replaceAll() |
|---|---|---|
| Replaces | First occurrence | All occurrences|
| Global flag (g) | Required for replacing all occurrences | Not required, all occurrences replaced by default |
| Browser support | Widely supported | Modern browsers (consider polyfills for older browsers) |

### nullish coalescing operator (??)

The `??` operator in JavaScript is known as the nullish coalescing operator. It provides a concise way to handle default values when dealing with potentially null or undefined values.

#### Functionality:

The `??` operator evaluates its left-hand operand. If the left-hand operand is not null or undefined, it returns that value. However, if the left-hand operand is either null or undefined, it returns the right-hand operand.

```
const value = null;
const defaultValue = "Default Value";
const result = value ?? defaultValue;
console.log(result); // Output: "Default Value"
```

In this example, because value is null, the ?? operator returns the defaultValue.

#### Key Differences from || (Logical OR):

The logical OR operator (||) also provides a way to handle default values. However, it treats values like 0, '' (empty string), and false as "falsy," and would return the right-hand operand in those cases.
The ?? operator only considers null and undefined as nullish, making it more suitable for situations where you need to differentiate between actual null or undefined values and other falsy values.


### what is spread operator?

The JavaScript spread operator (...) is a powerful and concise syntax that allows you to:

Expand elements of an iterable (like an array or object) into individual elements.
Copy, merge, or combine arrays and objects.
Pass multiple values into functions.

Syntax

`...iterable`

Common Use Cases

Copying Arrays

```
const arr1 = [1, 2, 3];
const arr2 = [...arr1]; // [1, 2, 3]
```

Merging Arrays

```
const arr1 = [1, 2];
const arr2 = [3, 4];
const merged = [...arr1, ...arr2]; // [1, 2, 3, 4]
```

Passing Array Elements as Function Arguments

```
const nums = [1, 2, 3];
Math.max(...nums); // 3
```

Copying Objects

```
const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1 }; // { a: 1, b: 2 }
```

Merging Objects

```
const obj1 = { a: 1 };
const obj2 = { b: 2 };
const merged = { ...obj1, ...obj2 }; // { a: 1, b: 2 }
```

Using in Destructuring

```
const [first, ...rest] = [1, 2, 3, 4];
// first = 1, rest = [2, 3, 4]
```

 Notes
- Only the own enumerable properties are copied for objects.
- It's a shallow copy – nested objects or arrays are not deeply cloned.

### what is difference between var, let and const?

`var`: Introduced before ES5. Function Scoped (Not block-scoped). Allows re-declaration and hoisting, which can lead to bugs.

```
function testVar(){
    var x = 10;
    if(true){
        var x = 20; // Same Variable! This will overwrite the previous x
        console.log(x); // Outputs: 20
    }
    console.log(x); // Outputs: 20, because var is function-scoped
}
```

`let`: Introduced in ES6. Block-Scoped - respects {} boundaries like if statements, loops. Cannot be redeclared in the same scope. Mutable (can be reassigned)

```
let a = 5;
a = 10; // This is a allowed

if(true) {
  let a = 20;   Different scope, so this is allowed
  console.log(a); // Outputs: 20
}
console.log(a); // Outputs: 10
```

`const`: Introduced in ES6. Block-Scoped like let. Cannot be reassigned after it's initial assignment. Good for defining constants and preventing accidental changes.
variables declared using `const` are ***read-only***. They are a constant value, which means that once a variable is assigned with `const`, it cannot be reassigned:

```
const name = "tux";
name = "Tux the Penguin"; // This line will throw an error because 'name' is a constant

const user = {age: 30};
user.age = 31; // This is allowed because 'user' is a mutable object. object reference is constant, but its properties can change.
```
