# Javascript

# What is JavaScript?

**JavaScript (JS)** is a **programming language** used to make websites **interactive and dynamic**.

### What JS can do:

- Show pop-ups (alert)
- Take user input (prompt)
- React to clicks, typing, scrolling
- Change HTML & CSS dynamically
- Build games, forms, chatbots, apps

### Role in Web Development:

- **HTML** → Structure
- **CSS** → Styling
- **JavaScript** → Logic / Behaviour

# How JavaScript Runs?

JavaScript runs in:

**1  Browser (using JavaScript Engine)**

Every browser has a **JavaScript Engine to convert javaScript code into machine understandable code** .

Examples:

- Google Chrome → **V8 Engine**
- Mozilla Firefox → SpiderMonkey
- cpp → compiler

### **What does JS Engine do?**

  Converts **JavaScript code → Machine code**

  JavaScript is **single-threaded so e**xecutes it step by step i.e., executes one line at a time.

   ****

**2  Server (using Node.js – later)**

For beginners → **Browser Console**

## JavaScript Output Methods

JavaScript can show output in **multiple ways**.

1. console.log()

```jsx
let age = 20;
console.log(age);

```

2.alert()

`alert()` displays a **popup message** on screen. User input is not available.

```jsx
alert("Welcome to JavaScript");
```

1. Prompt()

It is a way to take input when a popup pops and returns a value. 

```jsx
let name = prompt("Enter your name");
console.log(name);

```

Prompt always returns strings. Use Number() or parseInt() to convert to int.

```jsx
let age = Number(prompt("Enter age"));
let age = parseInt(prompt("Enter age"));
```

```jsx
let name = prompt("Enter your name");
alert(`Hello ${name}`);

let age=Number(prompt("Enter your age")) ;//by default string
if (isNaN(age)) {
  alert("Please enter a valid number");
} else {
  alert("Your age is " + age);
}
```

## What is a Variable?

A **variable** is a container that stores data.

## Types of Variable Declaration

---

| Features | Var(old-causes bug) | Let(ES6-2015) Modern and mutable | Const(fixed) Modern and immutable |
| --- | --- | --- | --- |
| Scope | Function or Global | Block Scope {} | Block Scoped {} |
| Redefinition/Reassignment(Changing value) | Allowed | Allowed | Not allowed |
| Redeclaration | Allowed | Not allowed(Syntax error) | Not allowed |
| Hoisting | Yes(as undefined) | Yes(as TDZ- Temporal Dead Zone) | Temporal Dead Zone |

```jsx
var x = 10;
var x = 20; // Redeclaration: Allowed
x = 30;     // Reassignment: Allowed
console.log(x); // 30
```

```jsx
let y = 10;
// let y = 20; // Uncaught SyntaxError: Identifier 'y' has already been declared
y = 30;        // Reassignment: Allowed
console.log(y); // 30
```

# Hoisting and Temporal Dead Zone

## What is Hoisting?

**Hoisting** is JavaScript’s default behavior of **moving declarations to the top of their scope during the memory creation phase** *before code execution*.

- **Only declarations are hoisted**
- **Not initializations**

## Hoisting happens in Memory Creation Phase

### JavaScript Execution Phases

When JS runs code, it happens in **2 phases**:

### Phase 1: Memory Creation Phase

- Variables are allocated memory
- Functions are stored completely

### Phase 2: Execution Phase

- Code runs line by line
- Values are assigned

  Hoisting happens in **Phase 1**

## Hoisting with `var`

Before hoisting on declaration:

```jsx
console.log(a);
var a = 10;
```

After hoisting on declaration:

```jsx
// Memory phase
var a = undefined;

// Execution phase
console.log(a); // undefined
a = 10;
```

var(only the declaration) is hoisted and initialized with undefined.

Hence output is **undefined**

## Hoisting with `let`

Before hoisting on declaration:

```jsx
console.log(a);
let a = 10;

```

```jsx
console.log(addtwo(5));
let addtwo=function(num){
    return num+2;
}
```

### This introduces to Temporal Dead Zone (TDZ)

**Temporal Dead Zone (TDZ)** is the **time between variable creation and its initialization where the variable cannot be accessed**.

This applies to:

- `let`
- `const`

### Why TDZ Exists?

TDZ exists to:

- Prevent usage before declaration
- Reduce bugs
- Enforce clean coding

After hoisting on declaration:

```jsx
ReferenceError: Cannot access 'a' before initialization
```

Without TDZ → silent bugs

With TDZ → clear error

## Hoisting with `const`

Before Hoisting:

```jsx
console.log(pi);
const pi =3.14;
```

Output after hoisting:

```
ReferenceError
```

### Rules for `const`:

    Must be initialized immediately

```jsx
const a;// ❌ SyntaxError
```

# VARIABLE NAMING RULES

### Naming Convention allowed-

- Letters (a–z, A–Z)
- Numbers at center only
- `_` underscore
- `$` dollar sign

### Naming Convention not allowed-

- Cannot start with number
- No spaces
- No special characters (`@ #`)

# Datatypes and categories

### 1 Primitive (Stored by VALUE)

- String(Immutable)
- Number
- Boolean
- Undefined
- Null
- Symbol
- BigInt

### 2 Non-Primitive (Stored by REFERENCE)

- Object
- Array
- Function

# OPERATORS IN JAVASCRIPT

| Arithmetic Operator | +,-,*,/,%,** |
| --- | --- |
| Assignment Operator | =,+=,-=,*=,/= |
| Comparison Operator | >,<,≥,≤ |
| Logical Operator | &&,!,|| |
| Unary Operator | ++,— |
| typeof Operator | typeof(true) |

# EQUALITY & COMPARISON

## 1 Loose Equality (`==`)

Compares **value only**, ignores the data type.

```jsx
5 == "5"; // true
```

## 2 Strict Equality (`===`)

Compares **value and data type**.

```jsx
5 === "5"; // false
```

## 3 Not Equal Operators(!=, !==)

```jsx

5 != "5";  // false
5 !== "5"; // true
```

### Examples-

null == undefined;  // true
null === undefined; // false

0 == false;  // true
0 === false; // false

# **Conditional Statements**

## If Statement

Executes a block of code **only if the condition is true**.

### Syntax

```jsx
if (condition) {
  // code
}
```

## If–else Statement

### Syntax

```jsx
if (condition) {
  // runs if true
} else {
  // runs if false
}
```

## Switch Statement

Used when you compare **one value against many cases**.

### Syntax

```jsx
switch (expression) {
  case value1:
    // code
    break;
  case value2:
    // code
    break;
  default:
    // code
}

```

### Why `break` is important?

Without `break`, execution **falls through**.

# Loops

Loops are used to **repeat code** until a condition is met.

### for loop

**Example**

```jsx
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
```

### while loop

**Example**

```jsx
let i = 1;

while (i <= 5) {
  console.log(i);
  i++;
}
```

### do while loop

Runs **at least once**, even if condition is false.

**Example**

```jsx
let i = 10;

do {
  console.log(i);
  i++;
} while (i <= 5);

```

### for–in Loop

Used to iterate over **keys/indexes and return the keys of any object**.

It works with objects.

Example(Object)

```jsx
let user = { name: "Anjali", age: 20 };

for (let key in user) {
  console.log(key, user[key]);
}
```

### for of Loop

Used to iterate over values in arrays, string, maps, sets.

Example(Array)

```jsx
let nums = [10, 20, 30];

for (let num of nums) {
  console.log(num);
}
```

### break Statement

Stops the loop completely.

Example

```jsx
for (let i = 1; i <= 5; i++) {
  if (i === 3) break;
  console.log(i);
}
```

### continue Statement

Skips the **current iteration**, continues next one.

Example

```jsx
for (let i = 1; i <= 5; i++) {
  if (i === 3) continue;
  console.log(i);
}
```

## Template Literals

A **Template Literal** is a modern way to write strings in JavaScript using **backticks** ``` instead of quotes.

```jsx
let msg = `Hello World`;
```

### String Interpolation

**String Interpolation** means inserting **variables or expressions directly inside a string**.

```jsx
let name = "Anjali";
let age = 20;

console.log(`My name is ${name} and my age is ${age}`);
```

```jsx
let text = `Hello
How are you?`;
```

### String

A **string** is a sequence of characters used to represent text.
Strings are **immutable-**Once created, characters cannot be changed directly.

0_indexed indexing.

```jsx
let str = "Hello";
str[0] = "h";   // ❌ No effect
```

### String Length

```jsx
let str = "Hello";
console.log(str.length); // 5
```

### String Methods

1. toUpperCase

Converts string to uppercase.

```jsx
"hello".toUpperCase(); // "HELLO"
```

1. toLowerCase

       Converts string to uppercase.

```jsx
"HELLO".toLowerCase(); // "hello"
```

1. trim

       Removes spaces from start & end.

It Does NOT remove middle spaces.

```jsx
"   hi   ".trim(); // "hi"
```

1. Slice
    
    Extracts part of string.
    
    It Supports negative index.
    
    ```jsx
    let str = "JavaScript";
    str.slice(0, 4); // "Java"
    str.slice(-6); // "Script"
    ```
    
2. substring(start, end)
    
    Similar to slice but no negative index allowed.
    
    ```jsx
    str.substring(0, 4); // "Java"
    ```
    
3. replace
    
    Replaces first occurrence.
    

```jsx
"Hello World".replace("World", "JS");
// "Hello JS"
```

1. replaceAll
    
    Replaces all occurrence.
    
    ```jsx
    "ha ha ha".replaceAll("ha", "hi");
    // "hi hi hi"
    ```
    
2. concat
    
    Joins Strings.
    
    ```jsx
    "Hello".concat(" ", "World");
    // "Hello World"
    ```
    
3. includes
    
    Checks if substring exists. It is case sensitive.
    
    ```jsx
    "JavaScript".includes("Script"); // true
    ```
    
4. startsWith
    
    ```jsx
    "Hello".startsWith("He"); // true
    ```
    
5. endsWith
    
    ```jsx
    "Hello".endsWith("lo"); // true
    ```
    
6. indexOf
    
    Returns position of first occurrence.
    
    ```jsx
    "banana".indexOf("a"); // 1
    ```
    
7. lastIndexOf
    
    ```jsx
    "banana".lastIndexOf("a"); // 5
    ```
    
8. charAt(index)
    
    Returns character at position.
    
    ```jsx
    "Hello".charAt(1); // "e"
    ```
    
9. split
    
    Converts string → array.
    
    ```jsx
    "apple,banana,mango".split(",");
    // ["apple", "banana", "mango"]
    ```
    
10. repeat
    
    Repeats string.
    
    ```jsx
    "Hi ".repeat(3);
    // "Hi Hi Hi "
    ```
    

17 length

```jsx
let str = "Java";
str.length; // 4
```

### Arrays

An **array** is a collection of multiple values stored in a single variable.

```jsx
let data = [10, "Hello", true, null];
```

### Ways to create array

1. Array Literal
    
    ```jsx
    let arr = [1, 2, 3];
    ```
    
2. Using array constructor

```jsx
let arr = new Array(1, 2, 3);
```

### Array Methods

## 1. push

Adds element(s) to the end of array.

```jsx
letarr= [1,2,3];

arr.push(4);
// [1, 2, 3, 4]
```

---

## 2. pop

Removes last element.

```jsx
letarr= [1,2,3];

arr.pop();

// [1, 2]
```

---

## 3. unshift

Adds element(s) to the beginning.

```jsx
letarr= [2,3];

arr.unshift(1);

// [1, 2, 3]
```

---

## 4. shift

Removes first element.

```jsx
letarr= [1,2,3];

arr.shift();

// [2, 3]
```

---

## 5. slice

Returns a portion of array (no change to original).

```jsx
letarr= [10,20,30,40];

arr.slice(1,3);

// [20, 30]
```

---

## 6. splice

Adds / removes / replaces elements.

```jsx
letarr= [1,2,3,4];

arr.splice(1,2);

// [1, 4]
```

Insert example:

```jsx
letarr= [1,3,4];

arr.splice(1,0,2);

// [1, 2, 3, 4]
```

---

## 7. concat

Joins arrays.

```jsx
leta= [1,2];
letb= [3,4];

a.concat(b);

// [1, 2, 3, 4]
```

---

## 8. indexOf

Returns first index of element.

```jsx
[10,20,30].indexOf(20);

// 1
```

If not found → `-1`

---

## 9. includes

Checks if element exists.

```jsx
[1,2,3].includes(2);

// true
```

---

## 10. join

Converts array → string.

```jsx
["a","b","c"].join("-");

// "a-b-c"
```

---

## 11. reverse

Reverses array in place.

```jsx
[1,2,3].reverse();

// [3, 2, 1]
```

---

## 12. sort

Sorts array.

```jsx
[3,1,2].sort();

// [1, 2, 3]
```

Numeric sort:

```jsx
[10,2,5].sort((a,b) =>a-b);

// [2, 5, 10]
```

---

## 13. forEach

Runs function for each element.

```jsx
[1,2,3].forEach(x =>console.log(x));

// 1 2 3
```

---

## 14. map

Creates new array with transformed values.

```jsx
letresult= [1,2,3].map(x =>x*2);

// [2, 4, 6]
```

---

## 15. filter

Returns elements that satisfy condition.

```jsx
leteven= [1,2,3,4].filter(x =>x%2===0);

// [2, 4]
```

---

## 16. reduce

Reduces array to a single value.

```jsx
letsum= [1,2,3,4].reduce((acc,cur) =>acc+cur,0);

// 10
```

---

## 17. find

Returns first matching element.

```jsx
[1,3,5,6].find(x =>x%2===0);

// 6
```

---

## 18. findIndex

Returns index of first match.

```jsx
[1,3,5,6].findIndex(x =>x%2===0);

// 3
```

---

## 19. every

Checks if ALL elements satisfy condition.

```jsx
[2,4,6].every(x =>x%2===0);

// true
```

---

## 20. some

Checks if AT LEAST ONE element satisfies condition.

```jsx
[1,3,4].some(x =>x%2===0);

// true
```

### Iteration Methods

1. for Each(callback function/higher order function)

   Runs the callback function for each element. It does not return new array 

```jsx
let arr = [1, 2, 3];

arr.forEach(function(num) {
  console.log(num);
});
```

1. map()
    
    Creates a new array by transforming elements. It return a new array.
    
    ```jsx
    let arr = [1, 2, 3];
    
    let doubled = arr.map(x => x * 2);
    // [2, 4, 6]
    ```
    

4. filter()

Return element that satisfy condition.

```jsx
let arr = [1, 2, 3, 4];

let even = arr.filter(x => x % 2 === 0);
// [2, 4]
```

1. reduce
    
    Reduces array to a single value.
    
    ```jsx
    let arr = [1, 2, 3, 4];
    
    let sum = arr.reduce((acc, curr) => acc + curr, 0);
    // 10
    ```
    

### Reference Types

Arrays are reference types.

```jsx
let a = [1, 2];
let b = a;

b[0] = 99;

console.log(a); // [99, 2]
```

Firstly,

**What is destructuring?**
Taking values from an **array or object** and storing them in **variables easily**.

## Array Destructuring

It extracts values **based on position (index)**.

Normally

```jsx
let arr = [10, 20, 30];

let a = arr[0];
let b = arr[1];
let c = arr[2];

console.log(a, b, c);
```

Using Array Destructuring

```jsx
let arr=[10,20,30];
let [a,b,c]=arr;
console.log(arr) //10,20,30

let arr = [10];
let [a, b = 5] = arr;
console.log(a, b);
```

## Object Destructuring

It extracts values **based on property names**.

Normally,

```jsx
let person = {
  name: "Anjali",
  age: 20
};

let name = person.name;
let age = person.age;

console.log(name, age);
```

Using Object Destructuring,

```jsx
let person = {
  name: "Anjali",
  age: 20
};
let {name, age} = person;
console.log(name, age);

let person = {
  name: "Anjali"
};
let {name, age = 18} = person;
console.log(name, age);
```
