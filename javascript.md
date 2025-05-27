---
title: Collection of JavaScript Interview Questions
author: Jacob Nelson
date: 2024-03-14
tags: [javascript, tutorial, interview]
---

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
