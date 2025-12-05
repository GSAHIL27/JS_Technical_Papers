# let, var, const in JavaScript

## var - Old Way (Avoid)

Function-scoped, can be re-declared, hoisted.

```javascript
var x = 10;
var x = 20; // No error, re-declaration allowed

if (true) {
  var y = 30;
}
console.log(y); // 30 (no block scope)

console.log(z); // undefined (hoisted)
var z = 40;
```

## let - Modern, Mutable

Block-scoped, cannot be re-declared in same scope, not initialized when hoisted.

```javascript
let a = 10;
// let a = 20; // Error: Identifier 'a' has already been declared

if (true) {
  let b = 30;
  console.log(b); // 30
}
// console.log(b); // Error: b is not defined

// console.log(c); // Error: Cannot access before initialization
let c = 40;

let count = 0;
count = 5; // Allowed to reassign
```

## const - Modern, Immutable Binding

Block-scoped, cannot be re-declared or reassigned, must be initialized.

```javascript
const PI = 3.14159;
// PI = 3.14; // Error: Assignment to constant variable

// const empty; // Error: Missing initializer

if (true) {
  const MAX = 100;
  console.log(MAX); // 100
}
// console.log(MAX); // Error: MAX is not defined
```

## const with Objects and Arrays

`const` prevents reassignment, but object/array contents can change.

```javascript
const person = { name: "John" };
person.name = "Jane"; // ✓ Allowed
person.age = 30; // ✓ Allowed
// person = {}; // ✗ Error: Assignment to constant

const numbers = [1, 2, 3];
numbers.push(4); // ✓ Allowed
numbers[0] = 10; // ✓ Allowed
// numbers = []; // ✗ Error: Assignment to constant
```

## Comparison Table

| Feature | var | let | const |
|---------|-----|-----|-------|
| Scope | Function | Block | Block |
| Re-declare | Yes | No | No |
| Reassign | Yes | Yes | No |
| Hoisted | Yes (initialized undefined) | Yes (not initialized) | Yes (not initialized) |
| Temporal Dead Zone | No | Yes | Yes |

## When to Use What

```javascript
// Use const by default
const API_URL = "https://api.example.com";
const user = { id: 1 };

// Use let when you need to reassign
let counter = 0;
for (let i = 0; i < 5; i++) {
  counter += i;
}

let status = "pending";
if (counter > 10) {
  status = "complete";
}

// Never use var in modern JavaScript
```

## Loop Scope Issue with var

```javascript
// var - all callbacks share same i
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 100);
}
// Output: 3, 3, 3

// let - each iteration has its own i
for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 100);
}
// Output: 0, 1, 2
```