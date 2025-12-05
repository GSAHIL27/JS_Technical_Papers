# Datatypes in JavaScript


## Different Datatypes in JavaScript

Javascript has two main categories of datatypes:

1. Primitive Datatypes- stored directly in memory, immutable
2. Non-Primitive Datatypes- objects stored by refrence, mutable

## 1.Primitive Datatypes

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

### 1.1 String

Used for textual data.


let name = "Sahil";
let greeting = `Hello ${name}`; 
Output: Hello Sahil


Strings are immutable:

let s = "abc";
s[0] = "z";  
console.log(s);

### 1.2 Number

Represents integers and floating numbers.


let age = 23;
let price = 99.99;

console.log(10 / 0); // Infinity
console.log("abc" * 5); // NaN


JavaScript uses double-precision floating point, so beware of rounding:


console.log(0.1 + 0.2); // 0.30000000000000004


### 1.3 Boolean

Represents true/false conditions.


let isAdmin = false;
let isLoggedIn = true;

console.log(5 > 3); // true


Used in conditions, comparisons, and logic.


### 1.4 Undefined

A variable declared but not assigned.


let x;
console.log(x); // undefined


Functions return undefined by default if no return statement exists.


function test() {}
console.log(test()); // undefined


### 1.5 Null

Intentional absence of value.


let user = null;


null is of type "object" due to a historical JS bug.


### 1.6 BigInt

Used for extremely large integers.


let big = 9007199254740991n; // n at end creates BigInt
console.log(big + 10n);


BigInt cannot mix with normal numbers:


10n + 5; // TypeError


### 1.7 Symbol

Used for unique identifiers in objects.


const id = Symbol("userId");

const user = {
  name: "Sahil",
  [id]: 88
};

console.log(user[id]); // 88


Every Symbol is unique:


Symbol("a") === Symbol("a"); // false


## 2. Non-Primitive Datatypes

These are mutable, and stored by reference.

- Object
- Array
- Function


### 2.1 Object


const user = {
  name: "Sahil",
  age: 22
};

user.age = 23; // modifying is allowed
console.log(user);


Objects can store mixed datatypes.


### 2.2 Array

Ordered list of values.


let nums = [10, 20, 30];
nums.push(40);

console.log(nums); // [10, 20, 30, 40]


Arrays are mutable:


const arr = ["a", "b"];
arr[0] = "z";
console.log(arr); // ["z", "b"]


### 2.3 Function

Functions themselves are objects with callable behavior.


function add(a, b) {
  return a + b;
}

console.log(add(5, 3)); // 8


Functions can be stored, passed, returned


function wrapper(fn) {
  return fn(10);
}

console.log(wrapper(x => x * 2)); // 20
