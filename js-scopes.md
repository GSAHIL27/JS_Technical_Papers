# Scopes in JavaScript

Scope determines where variables are accessible in your code.

## Global Scope

Variables declared outside any function or block.

```javascript
let globalVar = "I'm global";

function test() {
  console.log(globalVar); // Accessible
}

test(); // "I'm global"
console.log(globalVar); // "I'm global"
```

## Function Scope

Variables declared inside a function are only accessible within that function.

```javascript
function myFunction() {
  let functionVar = "I'm local";
  console.log(functionVar); // Works
}

myFunction();
// console.log(functionVar); // Error: functionVar is not defined
```

## Block Scope

Variables declared with `let` and `const` inside `{}` are block-scoped.

```javascript
if (true) {
  let blockVar = "I'm in a block";
  console.log(blockVar); // Works
}

// console.log(blockVar); // Error: blockVar is not defined
```

```javascript
for (let i = 0; i < 3; i++) {
  console.log(i); // 0, 1, 2
}

// console.log(i); // Error: i is not defined
```

## Scope Chain

Inner scopes can access outer scope variables.

```javascript
let outer = "outer";

function level1() {
  let middle = "middle";
  
  function level2() {
    let inner = "inner";
    console.log(outer);  // accessible
    console.log(middle); // accessible
    console.log(inner);  // accessible
  }
  
  level2();
  // console.log(inner); // not accessible
}

level1();
```

## Lexical Scope

Functions are executed using the scope where they were defined, not where they are called.

```javascript
let x = "global";

function outer() {
  let x = "outer";
  
  function inner() {
    console.log(x); // "outer" (uses definition scope)
  }
  
  return inner;
}

let x = "different global";
let fn = outer();
fn(); // "outer"
```

## Variable Shadowing

Inner scope variables can shadow outer scope variables with the same name.

```javascript
let name = "Global";

function test() {
  let name = "Local";
  console.log(name); // "Local"
}

test();
console.log(name); // "Global"
```

## Closure Example

Inner functions remember their scope even after outer function returns.

```javascript
function counter() {
  let count = 0;
  
  return function() {
    count++;
    return count;
  };
}

let increment = counter();
console.log(increment()); // 1
console.log(increment()); // 2
console.log(increment()); // 3
```
