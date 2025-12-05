# JavaScript Data Types

JavaScript has 8 data types: 7 primitive and 1 complex.

## Primitive Types

### 1. Number
```javascript
let age = 25;
let price = 99.99;
let negative = -10;
let infinity = Infinity;
let notANumber = NaN;

console.log(typeof age); // "number"
```

### 2. String
```javascript
let name = "John";
let greeting = 'Hello';
let template = `Hi ${name}`;

console.log(typeof name); // "string"
```

### 3. Boolean
```javascript
let isActive = true;
let hasPermission = false;

console.log(typeof isActive); // "boolean"
```

### 4. Undefined
```javascript
let x;
let y = undefined;

console.log(typeof x); // "undefined"
```

### 5. Null
```javascript
let empty = null;

console.log(typeof empty); // "object" (historical bug in JS)
console.log(empty === null); // true
```

### 6. BigInt
```javascript
let big = 9007199254740991n;
let another = BigInt(9007199254740991);

console.log(typeof big); // "bigint"
```

### 7. Symbol
```javascript
let id1 = Symbol("id");
let id2 = Symbol("id");

console.log(id1 === id2); // false (always unique)
console.log(typeof id1); // "symbol"
```

## Complex Type

### 8. Object
```javascript
let person = { name: "Alice", age: 30 };
let colors = ["red", "blue", "green"];
let date = new Date();
let regex = /pattern/;

console.log(typeof person); // "object"
console.log(typeof colors); // "object"
console.log(Array.isArray(colors)); // true
```

## Type Checking

```javascript
// Use typeof for primitives
console.log(typeof 42); // "number"
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
