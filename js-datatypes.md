# JavaScript Data Types

Javascript has two main categories of datatypes:

1. Primitive Datatypes- stored directly in memory, immutable
2. Non-Primitive Datatypes- objects stored by refrence, mutable

## 1.Primitive Types

Primitive values cannot be changed once created.
If you modify them, JS actually creates a new value.

Primitive types:

- String
- Number
- Boolean
- Undefined
- Null
- BigInt
- Symbol

### 1.1 Number

Represents integers and floating numbers.

```javascript
let age = 23;
let price = 99.99;
let negative = -10;
let infinity = Infinity;
let notANumber = NaN;

console.log(typeof age); // "number"
```

JavaScript uses double-precision floating point, so beware of rounding:

### 1.2 String

Used for textual data.

```javascript
let name = "Sahil";
let greeting = 'Hello';
let template = `Hi ${name}`;

console.log(typeof name); // "string"
```

### 1.3 Boolean

Represents true/false conditions.

```javascript
let isActive = true;
let hasPermission = false;

console.log(typeof isActive); // "boolean"
```

Used in conditions, comparisons, and logic.

### 1.4 Undefined

A variable declared but not assigned.

```javascript
let x;
let y = undefined;

console.log(typeof x); // "undefined"
```

Functions return undefined by default if no return statement exists.


### 1.5 Null

Intentional absence of value.

```javascript
let empty = null;

console.log(typeof empty); // "object" 
console.log(empty === null); // true
```

null is of type "object" due to a historical JS bug.

### 1.6 BigInt

Used for extremely large integers.

```javascript
let big = 9007199254740991n;
let another = BigInt(9007199254740991);

console.log(typeof big); // "bigint"
```

BigInt cannot mix with normal numbers:

### 1.7 Symbol

Used for unique identifiers in objects.

```javascript
let id1 = Symbol("id");
let id2 = Symbol("id");

console.log(id1 === id2); // false (always unique)
console.log(typeof id1); // "symbol"
```

Every Symbol is unique:

## 2. Non-Primitive Datatypes

These are mutable, and stored by reference.

- Object
- Array
- Function

### 2.1 Object
```javascript
let person = { name: "Sahil", age: 23 };
let colors = ["red", "blue", "green"];
let date = new Date();
let regex = /pattern/;

console.log(typeof person); // "object"
console.log(typeof colors); // "object"
console.log(Array.isArray(colors)); // true
```
Objects can store mixed datatypes.
Array and Function are a type of Object


## Type Checking

```javascript
// Use typeof for primitives
console.log(typeof 27); // "number"
console.log(typeof "text"); // "string"

// Special cases
console.log(typeof null); // "object" (bug)
console.log(typeof []); // "object"
console.log(typeof function(){}); // "function"

// Better checks
console.log(Array.isArray([])); // true
console.log(null === null); // true
```

## Type Conversion

```javascript
// String conversion
String(123); // "123"
String(true); // "true"

// Number conversion
Number("456"); // 456
Number("abc"); // NaN
parseInt("10px"); // 10

// Boolean conversion
Boolean(1); // true
Boolean(0); // false
Boolean(""); // false
Boolean("text"); // true
```
