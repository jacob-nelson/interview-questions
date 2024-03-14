---
title: Collection of JavaScript Interview Questions
author: Jacob Nelson
date: 2024-03-14
tags: [javascript, tutorial, interview]
---

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
