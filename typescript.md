### What is TypeScript?
TypeScript is a superset of JavaScript that adds static typing and other
features to the language.
### Explain the benefits of using TypeScript.
TypeScript offers advantages like static typing, improved tooling, better code organization, and enhanced maintainability over plain JavaScript.
### What is a TypeScript interface? How are they used?
- An interface in TypeScript is a way to define the structure of an object. They
describe the properties and methods that an object should have, without
implementing the actual functionality.
- Interfaces are defined using the interface keyword followed by a name
and curly braces containing the properties and methods.
- They specify the names, types, and optional/required status of properties and
method signatures (arguments and return types).
- Interfaces themselves don't directly create objects; they serve as contracts
that objects must adhere to.
### What is the difference between let and const in TypeScript?
let is used to declare variables that can be reassigned, while const is used for variables that cannot be reassigned once they are initialized.
### What are TypeScript types?
Types in TypeScript allow you to specify the data type of a variable, parameter, or return value.
### What are custom types?
custom types are user-defined data structures that go beyond the basic built-in types like number, string, and boolean. They allow you to create complex data structures that represent specific entities or concepts within your application, improving code clarity, type safety, and maintainability. custom types help to define aliases for existing types or create new types using unions, intersections, tuples, and more.
### Explain the concept of static typing in TypeScript.
Static typing means specifying the data types of variables at compile time.
TypeScript helps catch type-related errors early in the development process.

### What is the "any" type in TypeScript?
The "any" type in TypeScript allows variables to have any data type. It is often used when the type of a variable is not known during development.
### What is a union type in TypeScript?
- A union type in TypeScript allows a variable to have multiple types. It is represented using the | operator. 25. What is TypeScript's "tuple" type?
- A tuple in TypeScript is an ordered array with a fixed number of elements, each of which can have a different data type.
### What is the "never" type in TypeScript?
- The "never" type is used to represent values that never occur. It is often used
in functions that throw exceptions or enter infinite loops. 27. Describe TypeScript's type assertion.
 - Type assertion in TypeScript is a way to tell the compiler about the type of a variable when the developer knows more about its type than the compiler does.
### Explain the "class" and "inheritance" concepts in TypeScript.
Classes in TypeScript allow you to create objects with properties and methods. Inheritance enables a class to inherit properties and methods from another class.
### Explain the difference between any and unknown types.
- Both any and unknown are special types in TypeScript that allow you to work with values of unknown types. However, they have distinct meanings and uses:
- any essentially tells the compiler to disable type checking for that value. It allows you to assign any type of value to the variable without any warnings or errors.
- unknown represents a value whose type is unknown to the compiler. It's stricter than any but allows you to perform some operations safely.
### Explain basic concepts like null, undefined, and void types.
- null is a special value that represents the absence of any object value or the intentional absence of any reference.
- undefined is a primitive value that is used when a variable has been
declared but has not been assigned a value.
- void is a type that represents the absence of any type. It is often used as the
return type of function that does not return any value.
- While undefined and null are values that can be assigned to variables,
void is mainly used as a return type for functions.
### How do you perform basic operations like arrays and functions with type
annotations?
○ // Array of numbers
○ const numbers: number[] = [1, 2, 3]; ○
○ // Array of strings
○ const names: string[] = ["John", "Alice", "Bob"]; ○
○ // Array of any type (not recommended for production)
○ const mixedArray: any[] = [1, "hello", true];
32. How do you import and export modules in TypeScript?
○ you can use the import and export keywords to work with modules. 33. what is named export
○ A named export is a way to export specific variables, functions, or classes from a module in JavaScript. It allows you to give each exported entity a unique name, which you then use when importing it into another module.
### What is the default export
○ a default export is a way to export a single value (function, object, class,
etc.) from a module as the main or default export. This means you can import it using a simpler syntax compared to named exports.
i. Only one value can be exported as default per module.

ii. No curly braces are needed when importing the default export.
iii. Youcangiveanynametotheimportedvariablewhenimportingthe
default export.
iv. Default exports are suitable for situations where you have a single
core functionality or value to offer in a module.
### When to choose between named and default exports:
○ If you have a single main value to export, consider using a default export for simplicity.
○ If you need to export multiple functionalities or want more control over the import names, use named exports.
