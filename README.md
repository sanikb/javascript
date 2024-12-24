# JavaScript for Beginners

Welcome to the **JavaScript for Beginners** repository! This repository is designed to help you learn the basics of JavaScript through examples and practical implementations.

---

## Table of Contents

1. [Introduction and History of JavaScript](#introduction-and-history-of-javascript)
2. [Syntax of JavaScript and Overview](#syntax-of-javascript-and-overview)
3. [JavaScript Implementation](#javascript-implementation)
4. [How to Use HTML Tags in JavaScript](#how-to-use-html-tags-in-javascript)
5. [Var in JavaScript](#var-in-javascript)
6. [Global and Local Variables in JavaScript](#global-and-local-variables-in-javascript)
7. [Advanced `console.log`](#advanced-consolelog)

---

### 1. Introduction and History of JavaScript

JavaScript was developed by Brendan Eich in 1995 to make web pages interactive. Initially named Mocha, it was later renamed to JavaScript to reflect its similarity to Java.

```javascript
console.log("JavaScript was created in 1995!");
```

**Output:**
```
JavaScript was created in 1995!
```

---

### 2. Syntax of JavaScript and Overview

JavaScript uses a syntax similar to C and Java, making it beginner-friendly. Here’s a basic syntax overview:

```javascript
// This is a single-line comment
/*
This is a
multi-line comment
*/
let message = "Hello, World!";
console.log(message);
```

**Output:**
```
Hello, World!
```

---

### 3. JavaScript Implementation

You can implement JavaScript in your HTML using `<script>` tags.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>JavaScript Implementation</title>
</head>
<body>
  <h1>Check the console for output</h1>
  <script>
    console.log("JavaScript is implemented!");
  </script>
</body>
</html>
```

**Output (in Console):**
```
JavaScript is implemented!
```

---

### 4. How to Use HTML Tags in JavaScript

You can manipulate HTML elements dynamically using JavaScript.

```javascript
document.getElementById("demo").innerHTML = "Hello, JavaScript!";
```

**HTML:**
```html
<p id="demo"></p>
<script>
  document.getElementById("demo").innerHTML = "Hello, JavaScript!";
</script>
```

**Output in Browser:**
```
Hello, JavaScript!
```

---

### 5. Var in JavaScript

The `var` keyword is used to declare variables. However, its scope handling has some caveats.

```javascript
var x = 10;
if (true) {
  var x = 20;
  console.log(x); // 20
}
console.log(x); // 20
```

**Output:**
```
20
20
```

---

### 6. Global and Local Variables in JavaScript

Variables declared outside any function are global, while those inside a function are local.

```javascript
var globalVar = "I am global";

function test() {
  var localVar = "I am local";
  console.log(globalVar); // Accessible
  console.log(localVar);  // Accessible
}

test();
console.log(globalVar); // Accessible
// console.log(localVar); // Error: localVar is not defined
```

**Output:**
```
I am global
I am local
I am global
```

---

### 7. Advanced `console.log`

The `console.log` function can be used creatively to debug and format outputs.

```javascript
console.log("Simple Message");
console.log("Formatted: %cHello, styled log!", "color: red; font-size: 20px;");
console.table({ name: "John", age: 30 });
```

**Output:**
```
Simple Message
Formatted: Hello, styled log! (in red and large text)
Table:
name  | age
John  | 30
```

---

---

# 🚀 Difference Between `let`, `var`, and `const`

| Feature                | `var`                                       | `let`                                       | `const`                                     |
|------------------------|---------------------------------------------|---------------------------------------------|---------------------------------------------|
| **Scope**              | Function scope (if declared inside a function) or globally scoped | Block scope (if declared inside a block)   | Block scope (like `let`, but must be initialized) |
| **Hoisting**           | Hoisted to the top of the function or global scope, but not initialized | Hoisted to the top of the block, but not initialized | Hoisted to the top of the block, but not initialized |
| **Re-declaration**     | Can be re-declared in the same scope       | Cannot be re-declared in the same scope     | Cannot be re-declared or reassigned         |
| **Re-assignment**      | Can be reassigned                          | Can be reassigned                          | Cannot be reassigned once initialized       |
| **Initialization**     | Can be declared without initialization     | Can be declared without initialization     | Must be initialized when declared          |
| **Usage**              | Older way to declare variables             | Recommended for modern JavaScript use       | Used for constants or values that should not change |
| **Example**            | `var x = 10;`                              | `let y = 20;`                              | `const z = 30;`                             |
| **Output of re-assignment** | `x = 5;` reassigning is allowed          | `y = 10;` reassigning is allowed           | `z = 40;` will throw an error               |

---

### **Examples**

#### 1. **Example with `var`**

```javascript
var x = 10;
if (true) {
  var x = 20;  // Re-declaration and reassignment
}
console.log(x); // Output: 20
```

- **Explanation**: `var` is function-scoped, and it can be re-declared within the same scope. In this case, the value of `x` inside the `if` block changes the value of `x` globally.

---

#### 2. **Example with `let`**

```javascript
let y = 10;
if (true) {
  let y = 20;  // Block-scoped, separate from outer y
}
console.log(y); // Output: 10
```

- **Explanation**: `let` is block-scoped, so the `y` inside the `if` block does not affect the `y` outside. The output is `10`.

---

#### 3. **Example with `const`**

```javascript
const z = 30;
z = 40; // Error: Assignment to constant variable
```

- **Explanation**: `const` variables cannot be reassigned once initialized, so this will throw an error.

---

### **Key Takeaways**:

- **`var`**: Function-scoped, allows re-declaration and reassignment.
- **`let`**: Block-scoped, allows reassignment but not re-declaration in the same scope.
- **`const`**: Block-scoped, cannot be reassigned or re-declared. Used for constants.

This table provides a quick comparison for interviews and understanding the usage of `let`, `var`, and `const` in JavaScript.

# 🌟 Advanced JavaScript Console Methods 🚀

Welcome to the **Advanced JavaScript Console Methods** repository! This guide will help you understand and use advanced features of the `console` object in JavaScript to make debugging and logging more efficient. 

---

## 🌐 Table of Contents

1. [Console.log with Formatting](#-consolelog-with-formatting)
2. [Console.error and Console.warn](#-consoleerror-and-consolewarn)
3. [Console.table](#-consoletable)
4. [Console.assert](#-consoleassert)
5. [Console.group and Console.groupCollapsed](#-consolegroup-and-consolegroupcollapsed)
6. [Console.count](#-consolecount)
7. [Console.time and Console.timeEnd](#-consoletime-and-consoletimeend)
8. [Console.trace](#-consoletrace)

---

### 1. 🎨 Console.log with Formatting

You can add colors and styles to your console logs for better visibility.

```javascript
console.log("%cHello, styled log!", "color: blue; font-size: 16px; font-weight: bold;");
console.log("%cError log", "color: red; background-color: yellow; padding: 2px;");

<details>
  <summary>🖥️ Output</summary>

Styled messages in the console with specified colors, fonts, and sizes. 🎨

</details>

---

### 2. ⚠️ Console.error and Console.warn

Use `console.error` for errors and `console.warn` for warnings.

```javascript
console.error("❌ This is an error message");
console.warn("⚠️ This is a warning message");
```

<details>
  <summary>🖥️ Output</summary>

- **Error:** ❌ This is an error message
- **Warning:** ⚠️ This is a warning message

</details>

---

### 3. 📝 Console.table

`console.table` is great for displaying arrays or objects as tables.

```javascript
const users = [
  { name: "Alice", age: 25 },
  { name: "Bob", age: 30 }
];
console.table(users);
```

<details>
  <summary>🖥️ Output</summary>

A tabular display of the `users` array:
```
┌─────────┬──────────┬─────┐
│ (index) │   name   │ age │
├─────────┼──────────┼─────┤
│    0    │ 'Alice'  │ 25  │
│    1    │ 'Bob'    │ 30  │
└─────────┴──────────┴─────┘
```

</details>

---

### 4. 🛑 Console.assert

Use `console.assert` to log errors when a condition is `false`.

```javascript
const age = 15;
console.assert(age >= 18, "❌ Age must be 18 or older");
```

<details>
  <summary>🖥️ Output</summary>

```
Assertion failed: ❌ Age must be 18 or older
```

</details>

---

### 5. 🧩 Console.group and Console.groupCollapsed

Group related logs together for better organization.

```javascript
console.group("Group 1");
console.log("Message 1");
console.log("Message 2");
console.groupEnd();

console.groupCollapsed("Collapsed Group");
console.log("Hidden Message 1");
console.log("Hidden Message 2");
console.groupEnd();
```

<details>
  <summary>🖥️ Output</summary>

- **Group 1**: Messages are displayed together.
- **Collapsed Group**: Messages are hidden until expanded.

</details>

---

### 6. 🔢 Console.count

Count the number of times a specific label is logged.

```javascript
console.count("Counter");
console.count("Counter");
console.count("Another Counter");
console.count("Counter");
```

<details>
  <summary>🖥️ Output</summary>

```
Counter: 1
Counter: 2
Another Counter: 1
Counter: 3
```

</details>

---

### 7. ⏱️ Console.time and Console.timeEnd

Measure the time taken to execute a block of code.

```javascript
console.time("Timer");
for (let i = 0; i < 1000000; i++) {}
console.timeEnd("Timer");
```

<details>
  <summary>🖥️ Output</summary>

```
Timer: 3.123ms (Time may vary based on system performance)
```

</details>

---

### 8. 🧵 Console.trace

Print the stack trace of a function call.

```javascript
function first() {
  second();
}

function second() {
  console.trace("Stack trace");
}

first();
```

<details>
  <summary>🖥️ Output</summary>

```
Trace: Stack trace
    at second (<file_path>:line:column)
    at first (<file_path>:line:column)
    at <main execution context>
```

</details>

---

### 📋Arithmetic Operators Table

| Operator | Description           | Example      | Result |
|----------|-----------------------|--------------|--------|
| `+`      | Addition              | `5 + 3`      | `8`    |
| `-`      | Subtraction           | `5 - 3`      | `2`    |
| `*`      | Multiplication        | `5 * 3`      | `15`   |
| `/`      | Division              | `6 / 3`      | `2`    |
| `%`      | Modulus (Remainder)   | `5 % 2`      | `1`    |
| `**`     | Exponentiation (Power)| `5 ** 2`     | `25`   |

---

## 🖥️ Examples of JavaScript Arithmetic Operators

### 1️⃣ **Addition (`+`)**
The `+` operator adds two numbers together.

```javascript
let a = 5;
let b = 3;
console.log(a + b); // Output: 8
```

---

### 2️⃣ **Subtraction (`-`)**
The `-` operator subtracts the second number from the first.

```javascript
let a = 5;
let b = 3;
console.log(a - b); // Output: 2
```

---

### 3️⃣ **Multiplication (`*`)**
The `*` operator multiplies two numbers.

```javascript
let a = 5;
let b = 3;
console.log(a * b); // Output: 15
```

---

### 4️⃣ **Division (`/`)**
The `/` operator divides the first number by the second.

```javascript
let a = 6;
let b = 3;
console.log(a / b); // Output: 2
```

---

### 5️⃣ **Modulus (`%`)**
The `%` operator returns the remainder of the division.

```javascript
let a = 5;
let b = 2;
console.log(a % b); // Output: 1
```

---

### 6️⃣ **Exponentiation (`**`)**
The `**` operator raises the first number to the power of the second.

```javascript
let a = 5;
let b = 2;
console.log(a ** b); // Output: 25
```

---


# ✍️ JavaScript Assignment Operators 🖥️

This document explains **JavaScript Assignment Operators** with brief descriptions and code examples.

---

## 📋 Assignment Operators Table

| Operator | Description                       | Example         | Equivalent To      |
|----------|-----------------------------------|-----------------|--------------------|
| `=`      | Assigns a value to a variable     | `x = 5`         | `x = 5`           |
| `+=`     | Adds and assigns the result       | `x += 3`        | `x = x + 3`       |
| `-=`     | Subtracts and assigns the result  | `x -= 2`        | `x = x - 2`       |
| `*=`     | Multiplies and assigns the result | `x *= 4`        | `x = x * 4`       |
| `/=`     | Divides and assigns the result    | `x /= 2`        | `x = x / 2`       |
| `%=`     | Assigns the remainder of division | `x %= 3`        | `x = x % 3`       |
| `**=`    | Assigns the result of exponentiation | `x **= 2`   | `x = x ** 2`      |

---

## 🖥️ Examples of Assignment Operators

### 1️⃣ **Basic Assignment (`=`)**
Assigns a value to a variable.

```javascript
let x;
x = 5; 
console.log(x); // Output: 5
```

---

### 2️⃣ **Addition Assignment (`+=`)**
Adds a value to the variable and assigns the result.

```javascript
let x = 5;
x += 3; // Same as x = x + 3
console.log(x); // Output: 8
```

---

### 3️⃣ **Subtraction Assignment (`-=`)**
Subtracts a value from the variable and assigns the result.

```javascript
let x = 5;
x -= 2; // Same as x = x - 2
console.log(x); // Output: 3
```

---

### 4️⃣ **Multiplication Assignment (`*=`)**
Multiplies the variable by a value and assigns the result.

```javascript
let x = 5;
x *= 4; // Same as x = x * 4
console.log(x); // Output: 20
```

---

### 5️⃣ **Division Assignment (`/=`)**
Divides the variable by a value and assigns the result.

```javascript
let x = 10;
x /= 2; // Same as x = x / 2
console.log(x); // Output: 5
```

---

### 6️⃣ **Modulus Assignment (`%=`)**
Divides the variable and assigns the remainder.

```javascript
let x = 5;
x %= 3; // Same as x = x % 3
console.log(x); // Output: 2
```

---

### 7️⃣ **Exponentiation Assignment (`**=`)**
Raises the variable to the power of a value and assigns the result.

```javascript
let x = 2;
x **= 3; // Same as x = x ** 3
console.log(x); // Output: 8
```

---


# 🚀 JavaScript Comparison Operators 🔍

This document provides examples of JavaScript comparison operators, showcasing their functionality with simple code snippets.

---

## 📋 Comparison Operators Table

| Operator | Description                             | Example         | Result   |
|----------|-----------------------------------------|-----------------|----------|
| `==`     | Equal to (allows type conversion)       | `5 == '5'`      | `true`   |
| `===`    | Strict equal to (no type conversion)    | `5 === '5'`     | `false`  |
| `!=`     | Not equal to (allows type conversion)   | `5 != '5'`      | `false`  |
| `!==`    | Strict not equal to (no type conversion)| `5 !== '5'`     | `true`   |
| `>`      | Greater than                            | `5 > 3`         | `true`   |
| `<`      | Less than                               | `5 < 3`         | `false`  |
| `>=`     | Greater than or equal to               | `5 >= 5`        | `true`   |
| `<=`     | Less than or equal to                  | `5 <= 3`        | `false`  |

---

## 🖥️ Examples of JavaScript Comparison Operators

### 1️⃣ **Equal to (`==`)**
The `==` operator checks if two values are equal, allowing type conversion.

```javascript
let a = 5;
console.log(a == '5'); // true (type conversion happens)
```

---

### 2️⃣ **Strict Equal to (`===`)**
The `===` operator checks if two values are equal without type conversion.

```javascript
let a = 5;
console.log(a === '5'); // false (different types)
```

---

### 3️⃣ **Not Equal to (`!=`)**
The `!=` operator checks if two values are not equal, allowing type conversion.

```javascript
let a = 5;
console.log(a != '5'); // false (type conversion happens)
```

---

### 4️⃣ **Strict Not Equal to (`!==`)**
The `!==` operator checks if two values are not equal without type conversion.

```javascript
let a = 5;
console.log(a !== '5'); // true (different types)
```

---

### 5️⃣ **Greater Than (`>`)**
The `>` operator checks if the left operand is greater than the right operand.

```javascript
let a = 5;
console.log(a > 3); // true
```

---

### 6️⃣ **Less Than (`<`)**
The `<` operator checks if the left operand is less than the right operand.

```javascript
let a = 5;
console.log(a < 3); // false
```

---

### 7️⃣ **Greater Than or Equal to (`>=`)**
The `>=` operator checks if the left operand is greater than or equal to the right operand.

```javascript
let a = 5;
console.log(a >= 5); // true
```

---

### 8️⃣ **Less Than or Equal to (`<=`)**
The `<=` operator checks if the left operand is less than or equal to the right operand.

```javascript
let a = 5;
console.log(a <= 3); // false
```


# 🔗 JavaScript Logical Operators

JavaScript **Logical Operators** are used to perform logical operations and return Boolean results based on their operands.

---

## 📋 Logical Operators Table

| Operator | Description                       | Example                | Result       |
|----------|-----------------------------------|------------------------|--------------|
| `&&`     | Logical AND (returns `true` if both operands are true) | `true && false` | `false` |
| `||`     | Logical OR (returns `true` if at least one operand is true) | `true || false` | `true`  |
| `!`      | Logical NOT (inverts the Boolean value) | `!true`         | `false` |

---

## 🖥️ Examples of Logical Operators

### 1️⃣ **Logical AND (`&&`)**
The `&&` operator returns `true` if both operands are `true`.

```javascript
let a = true;
let b = false;

console.log(a && b); // Output: false
console.log(a && !b); // Output: true
```

---

### 2️⃣ **Logical OR (`||`)**
The `||` operator returns `true` if at least one operand is `true`.

```javascript
let a = true;
let b = false;

console.log(a || b); // Output: true
console.log(!a || b); // Output: false
```

---

### 3️⃣ **Logical NOT (`!`)**
The `!` operator inverts the Boolean value.

```javascript
let a = true;

console.log(!a); // Output: false
console.log(!false); // Output: true
```

---

## 🌟 Real-World Examples

1. **Form Validation**  
   Use logical operators to validate user input.

   ```javascript
   let username = "Pratham";
   let password = "12345";

   if (username && password) {
       console.log("Form is valid!");
   } else {
       console.log("Please fill all fields.");
   }
   ```

2. **Access Control**  
   Grant access based on multiple conditions.

   ```javascript
   let isAdmin = true;
   let isLoggedIn = true;

   if (isAdmin && isLoggedIn) {
       console.log("Welcome, Admin!");
   } else {
       console.log("Access denied.");
   }
   ```

---

## 📝 Interview Questions with Answers and Solutions

### 1️⃣ **Question**:  
What will be the output of the following code?

```javascript
console.log(true && false || !false);
```

**Answer**:  
`true`

**Solution**:  
1. Evaluate `!false` → `true`.  
2. Evaluate `true && false` → `false`.  
3. Evaluate `false || true` → `true`.

---

### 2️⃣ **Question**:  
Write a condition to check if a user is either an admin or a premium member.

**Solution**:  
```javascript
let isAdmin = false;
let isPremiumMember = true;

if (isAdmin || isPremiumMember) {
    console.log("Access granted.");
} else {
    console.log("Access denied.");
}
```

---

### 3️⃣ **Question**:  
What will the following code return?

```javascript
let a = false;
let b = true;
console.log(a || (b && !a));
```

**Answer**:  
`true`

**Solution**:  
1. Evaluate `!a` → `true`.  
2. Evaluate `b && true` → `true`.  
3. Evaluate `a || true` → `true`.

---

### 4️⃣ **Question**:  
How can you check if a number is in a specific range (e.g., between 10 and 20)?

**Solution**:  
```javascript
let number = 15;

if (number >= 10 && number <= 20) {
    console.log("Number is in the range.");
} else {
    console.log("Number is out of range.");
}
```

---

### 5️⃣ **Question**:  
What is the difference between `&&` and `||` operators in terms of short-circuit evaluation?

**Answer**:  
- `&&` stops evaluating as soon as the first `false` is encountered.  
- `||` stops evaluating as soon as the first `true` is encountered.

**Example**:  
```javascript
let a = false && console.log("This won't execute.");
let b = true || console.log("This won't execute.");
```

---

# JavaScript Ternary Operator 🌟

Welcome to the **JavaScript Ternary Operator** guide! This repository contains everything you need to understand and practice using the ternary operator in JavaScript. It includes examples, explanations, and **interview practice questions** to help you prepare for your next coding interview.

## 📜 Table of Contents

- [Introduction](#introduction)
- [Why Use the Ternary Operator?](#why-use-the-ternary-operator)
- [Examples of Ternary Operator](#examples-of-ternary-operator)
- [10 Interview Practice Questions](#10-interview-practice-questions)
- [Conclusion](#conclusion)

---

## 📝 Introduction

The **ternary operator** in JavaScript is a concise way to perform conditional checks. It evaluates a condition and returns one of two values based on whether the condition is `true` or `false`. It's a shorthand for `if-else` statements and can make your code more compact and readable when used correctly.

---

## 🚀 Why Use the Ternary Operator?

- **Concise**: The ternary operator allows you to express simple conditional logic in a single line.
- **Readability**: For basic conditions, it can make the code easier to read.
- **Assigning Values**: It’s often used for assigning values based on conditions.

---

## 💻 Examples of Ternary Operator

### Example 1: Basic Conditional Check

```javascript
let age = 20;
let canDrive = (age >= 18) ? "Yes" : "No";
console.log(canDrive); // Output: "Yes"
```

**Explanation:**  
The condition `(age >= 18)` checks if the age is greater than or equal to 18. If true, it returns `"Yes"`, otherwise `"No"`.

---

### Example 2: Nested Ternary Operator

```javascript
let score = 85;
let grade = (score >= 90) ? "A" : (score >= 80) ? "B" : (score >= 70) ? "C" : "D";
console.log(grade); // Output: "B"
```

**Explanation:**  
This example shows a nested ternary operator where multiple conditions are checked in sequence.

---

### Example 3: Using the Ternary Operator with Objects

```javascript
let number = 10;
let result = (number % 2 === 0) ? "Even" : "Odd";
console.log(result); // Output: "Even"
```

**Explanation:**  
Here, we check if the number is even or odd and return the corresponding result.

---

## 🎯 10 Interview Practice Questions

1. **What is the ternary operator in JavaScript?**  
   - The ternary operator is a shorthand for `if-else` statements that evaluates a condition and returns one of two values based on whether the condition is true or false.

2. **Can you write an example of a ternary operator?**  
   - Yes, here’s an example:
     ```javascript
     let x = 5;
     let result = (x > 3) ? "Greater" : "Smaller";
     console.log(result); // Output: "Greater"
     ```

3. **How do you handle multiple conditions using the ternary operator?**  
   - You can use nested ternary operators. Example:
     ```javascript
     let age = 25;
     let category = (age < 18) ? "Minor" : (age <= 60) ? "Adult" : "Senior";
     console.log(category); // Output: "Adult"
     ```

4. **What is the advantage of using the ternary operator over an `if-else` statement?**  
   - The ternary operator allows for more concise code, especially when the logic is simple and you need to return or assign values based on conditions.

5. **Can the ternary operator be used for assignments?**  
   - Yes, the ternary operator is often used for assigning values based on conditions, like:
     ```javascript
     let x = 10;
     let result = (x % 2 === 0) ? "Even" : "Odd";
     console.log(result); // Output: "Even"
     ```

6. **How would you rewrite a simple `if-else` statement using a ternary operator?**  
   - For example, converting:
     ```javascript
     if (x > 10) {
       console.log("Greater");
     } else {
       console.log("Smaller");
     }
     ```
     To a ternary operator:
     ```javascript
     console.log((x > 10) ? "Greater" : "Smaller");
     ```

7. **Can the ternary operator return more than just values?**  
   - Yes, it can return functions, objects, or other expressions. Example:
     ```javascript
     let greeting = (user) ? `Hello, ${user}!` : `Hello, Guest!`;
     console.log(greeting); // Output: "Hello, Guest!"
     ```

8. **What happens if you omit one part of the ternary operator?**  
   - Omitting one part will result in a syntax error. The ternary operator requires both the `true` and `false` expressions to function properly.

9. **Is it a good idea to use deeply nested ternary operators? Why or why not?**  
   - It's generally not recommended, as deeply nested ternary operators can make the code harder to read and understand. In such cases, `if-else` statements are preferred for clarity.

10. **What would happen if the ternary operator is used incorrectly, such as missing a colon?**  
    - Missing a colon (`:`) would result in a syntax error, as the ternary operator expects both the `true` and `false` expressions.

---

## 🎉 Conclusion

The **ternary operator** is a great tool to write concise conditional logic in JavaScript. It’s perfect for simple conditions and can make your code more readable when used appropriately. However, avoid overusing nested ternary operators to ensure your code remains clear and easy to understand.




# JavaScript Type Operators 📊

Welcome to the **JavaScript Type Operators** guide! This repository is dedicated to explaining and providing examples of **type operators** in JavaScript. Type operators are used to check and convert data types, which are fundamental for writing robust and error-free code.

## 📜 Table of Contents

- [Introduction](#introduction)
- [Type Operators in JavaScript](#type-operators-in-javascript)
  - [typeof](#typeof)
  - [instanceof](#instanceof)
  - [constructor](#constructor)
  - [Array.isArray](#arrayisarray)
- [10 Interview Practice Questions](#10-interview-practice-questions)
- [Conclusion](#conclusion)

---

## 📝 Introduction

In JavaScript, understanding the **type of data** is crucial for working with variables, functions, and objects. Type operators allow you to check or manipulate the types of values in your code.

---

## 🛠️ Type Operators in JavaScript

### 1. **`typeof` Operator 🔍**

The `typeof` operator is used to check the type of a variable or expression. It returns a string representing the type of the operand.

#### Syntax:
```javascript
typeof operand;
```

#### Example:

```javascript
let name = "John";
console.log(typeof name); // Output: "string"

let age = 30;
console.log(typeof age); // Output: "number"

let isStudent = true;
console.log(typeof isStudent); // Output: "boolean"
```

**Explanation:**
- The `typeof` operator checks the type of `name`, `age`, and `isStudent` and returns their respective types as strings.

---

### 2. **`instanceof` Operator 🔗**

The `instanceof` operator checks if an object is an instance of a specific class or constructor function.

#### Syntax:
```javascript
object instanceof constructor
```

#### Example:

```javascript
let arr = [1, 2, 3];
console.log(arr instanceof Array); // Output: true

let date = new Date();
console.log(date instanceof Date); // Output: true

let obj = {};
console.log(obj instanceof Object); // Output: true
```

**Explanation:**
- The `instanceof` operator checks if the object `arr` is an instance of `Array`, if `date` is an instance of `Date`, and if `obj` is an instance of `Object`.

---

### 3. **`constructor` Property 🏗️**

The `constructor` property of an object refers to the function that created the instance of that object.

#### Example:

```javascript
let person = { name: "Alice", age: 25 };
console.log(person.constructor); // Output: [Function: Object]

let date = new Date();
console.log(date.constructor); // Output: [Function: Date]
```

**Explanation:**
- The `constructor` property points to the function that created the object. For `person`, it's the `Object` constructor, and for `date`, it's the `Date` constructor.

---

### 4. **`Array.isArray()` Method 🧮**

The `Array.isArray()` method is used to check if a value is an array.

#### Syntax:
```javascript
Array.isArray(value);
```

#### Example:

```javascript
let arr = [1, 2, 3];
console.log(Array.isArray(arr)); // Output: true

let notArr = { name: "John" };
console.log(Array.isArray(notArr)); // Output: false
```

**Explanation:**
- `Array.isArray()` checks if the given value is an array. It returns `true` for arrays and `false` for other data types.

---

## 🎯 10 Interview Practice Questions

1. **What does the `typeof` operator do in JavaScript?**
   - The `typeof` operator is used to determine the type of a variable or expression. It returns a string representing the type, such as `"string"`, `"number"`, `"boolean"`, etc.

2. **What is the difference between `typeof` and `instanceof` in JavaScript?**
   - `typeof` is used to check the type of a primitive value (e.g., string, number), while `instanceof` is used to check if an object is an instance of a specific class or constructor function.

3. **How can you check if a value is an array in JavaScript?**
   - You can use `Array.isArray()` to check if a value is an array. Example: `Array.isArray([1, 2, 3])` returns `true`.

4. **What is the purpose of the `constructor` property in JavaScript?**
   - The `constructor` property refers to the function that created the instance of an object. For example, an object created using the `new Date()` constructor will have `Date` as its constructor.

5. **How would you check the type of a variable in JavaScript?**
   - You can use the `typeof` operator to check the type of a variable. Example: `typeof variable`.

6. **What will `typeof null` return in JavaScript?**
   - Surprisingly, `typeof null` returns `"object"`. This is a known JavaScript bug that has been present since its early versions.

7. **How can you check if an object is an instance of a specific constructor function?**
   - You can use the `instanceof` operator. Example: `object instanceof ConstructorFunction`.

8. **Can `typeof` be used to differentiate between an array and an object?**
   - No, `typeof` returns `"object"` for both arrays and objects. To differentiate, you should use `Array.isArray()`.

9. **What would `Array.isArray('hello')` return?**
   - It would return `false`, as a string is not an array.

10. **What is the output of `typeof NaN` in JavaScript?**
    - `typeof NaN` returns `"number"`. Although `NaN` stands for "Not a Number," it is technically considered a number in JavaScript.

---

## 🎉 Conclusion

Type operators in JavaScript, such as `typeof`, `instanceof`, `constructor`, and `Array.isArray()`, are essential tools for checking and manipulating data types. Understanding how and when to use these operators will help you write more reliable and efficient code.

Happy coding! 🚀

---

Here's a properly formatted **GitHub README** file for **JavaScript Logical Operators** practice tasks. It includes interactive **Show Answer** sections, where the answers will be revealed when clicked.

```markdown
# JavaScript Logical Operators Practice 🚀

Welcome to the **JavaScript Logical Operators Practice** guide! This file contains various tasks related to logical operators in JavaScript. Each task has a description, and you can reveal the solutions by clicking on the "Show Answer" button.

## 📜 Table of Contents

- [Task 1: Basic Practice](#task-1-basic-practice)
- [Task 2: Conditional Statements](#task-2-conditional-statements)
- [Task 3: Combining Logical Operators](#task-3-combining-logical-operators)

---

## 🔢 Task 1: Basic Practice (10 minutes)

**Problem:**  
Write a function that checks if a number is between 10 and 20 using the logical AND (`&&`) operator.

```javascript
function checkNumberInRange(number) {
  // Your code here
}
```

<details>
  <summary>Show Answer</summary>

  **Solution:**

  ```javascript
  function checkNumberInRange(number) {
    if (number >= 10 && number <= 20) {
      return "The number is between 10 and 20.";
    } else {
      return "The number is not between 10 and 20.";
    }
  }

  console.log(checkNumberInRange(15)); // Output: "The number is between 10 and 20."
  console.log(checkNumberInRange(25)); // Output: "The number is not between 10 and 20."
  ```

  **Explanation:**
  - The function checks if the number is greater than or equal to 10 **and** less than or equal to 20 using the `&&` logical operator.

</details>

---

## 🗳️ Task 2: Conditional Statements (10 minutes)

**Problem:**  
Create a simple program that checks if a user is allowed to vote based on their age and whether they have an ID.

```javascript
function canVote(age, hasID) {
  // Your code here
}
```

<details>
  <summary>Show Answer</summary>

  **Solution:**

  ```javascript
  function canVote(age, hasID) {
    if (age >= 18 && hasID) {
      return "You are allowed to vote!";
    } else {
      return "You are not allowed to vote.";
    }
  }

  console.log(canVote(20, true)); // Output: "You are allowed to vote!"
  console.log(canVote(17, true)); // Output: "You are not allowed to vote."
  console.log(canVote(20, false)); // Output: "You are not allowed to vote."
  ```

  **Explanation:**
  - The function checks if the user is **18 or older** **and** has an ID using the `&&` logical operator.

</details>

---

## 🔒 Task 3: Combining Logical Operators (10 minutes)

**Problem:**  
Write a function that checks if a person can access a restricted area. The criteria are:
- Must be **over 18** OR have a **special access badge**.
- Must **NOT** be on the restricted list.

```javascript
function canAccessRestrictedArea(age, hasBadge, isRestricted) {
  // Your code here
}
```

<details>
  <summary>Show Answer</summary>

  **Solution:**

  ```javascript
  function canAccessRestrictedArea(age, hasBadge, isRestricted) {
    if ((age > 18 || hasBadge) && !isRestricted) {
      return "Access granted.";
    } else {
      return "Access denied.";
    }
  }

  console.log(canAccessRestrictedArea(25, false, false)); // Output: "Access granted."
  console.log(canAccessRestrictedArea(17, true, false)); // Output: "Access granted."
  console.log(canAccessRestrictedArea(25, false, true)); // Output: "Access denied."
  ```

  **Explanation:**
  - The function checks if the person is either **over 18** or has a **special access badge** using the `||` operator.
  - It also ensures that the person is **not** on the restricted list using the `!` (not) operator.
  
</details>

---

## 🎉 Conclusion

Logical operators are essential in JavaScript for building conditional statements that allow your code to make decisions based on multiple conditions. Practice these tasks to strengthen your understanding of `&&`, `||`, and `!` operators.

# 🔄 Spread and Rest Operators in JavaScript

The `...` (three dots) can do two things:
- **Spread Operator**: Break things apart.
- **Rest Operator**: Gather things together.

---

## 🌟 Spread Operator

The **Spread Operator** (`...`) is used to copy or combine arrays or objects and pass elements as individual values.

### ✅ Example 1: Combining Arrays

```javascript
const fruits = ["apple", "banana"];
const vegetables = ["carrot", "broccoli"];
const food = [...fruits, ...vegetables];
console.log(food);
<details>
<summary>Detail</summary>

Here’s a **super simple explanation** of the **Spread and Rest Operators** with easy-to-understand examples:

```markdown
# 🔄 Spread and Rest Operators in JavaScript

The `...` (three dots) can do two things:
- **Spread Operator**: Break things apart.
- **Rest Operator**: Gather things together.

---

## 🌟 Spread Operator

The **Spread Operator** (`...`) is used to copy or combine arrays or objects and pass elements as individual values.

### ✅ Example 1: Combining Arrays

```javascript
const fruits = ["apple", "banana"];
const vegetables = ["carrot", "broccoli"];
const food = [...fruits, ...vegetables];
console.log(food);
```

**Output:**
```
["apple", "banana", "carrot", "broccoli"]
```

---

### ✅ Example 2: Copying an Object

```javascript
const person = { name: "John", age: 30 };
const newPerson = { ...person, occupation: "Teacher" };
console.log(newPerson);
```

**Output:**
```
{ name: "John", age: 30, occupation: "Teacher" }
```

---

## 🌟 Rest Operator

The **Rest Operator** (`...`) collects multiple items into a single array or object.

### ✅ Example 1: Function with Multiple Arguments

```javascript
function sum(...numbers) {
  console.log(numbers); // [1, 2, 3]
  return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3));
```

**Output:**
```
[1, 2, 3]
6
```

---

### ✅ Example 2: Destructuring with Rest

```javascript
const colors = ["red", "blue", "green", "yellow"];
const [first, second, ...others] = colors;
console.log(first);  // "red"
console.log(second); // "blue"
console.log(others); // ["green", "yellow"]
```

**Output:**
```
red
blue
["green", "yellow"]
```

---

## 🔑 Summary

- **Spread Operator (`...`)**: Breaks things into smaller parts (e.g., spreads an array).
- **Rest Operator (`...`)**: Gathers things into one group (e.g., collects extra arguments).

That’s it! Use these to simplify your JavaScript code! 🚀
```

</details>

<details>
<summary>Summary</summary>

- **Spread Operator (`...`)**: Breaks things into smaller parts, like spreading an array or copying an object.
- **Rest Operator (`...`)**: Gathers things into one group, like collecting arguments in a function or destructuring values.

These two operators help simplify your JavaScript code! 🚀
</details>


```

## 🌟 If-Else Statement

An **If-Else Statement** provides an alternative block of code that runs if the condition is `false`.

<details>
<summary>Click to see Output</summary>

### ✅ Example:

```javascript
const time = 15;
if (time < 12) {
  console.log("Good morning! 🌅");
} else {
  console.log("Good afternoon! 🌞");
}
```

**Output:**
```
Good afternoon! 🌞
```

</details>

---

## 🌟 If-Elif-Else Statement

An **If-Elif-Else Statement** allows you to check multiple conditions sequentially.

<details>
<summary>Click to see Output</summary>

### ✅ Example:

```javascript
const age = 18;
if (age < 18) {
  console.log("You are a minor. 👶");
} else if (age >= 18 && age < 60) {
  console.log("You are an adult. 👨‍💼");
} else {
  console.log("You are a senior citizen. 👵");
}
```

**Output:**
```
You are an adult. 👨‍💼
```

</details>

---

## 🌟 Switch Statement

A **Switch Statement** evaluates an expression and executes the corresponding case block based on the value of that expression.

<details>
<summary>Click to see Output</summary>

### ✅ Example:

```javascript
const day = 3;
switch (day) {
  case 1:
    console.log("Monday 🗓️");
    break;
  case 2:
    console.log("Tuesday 🗓️");
    break;
  case 3:
    console.log("Wednesday 🗓️");
    break;
  default:
    console.log("Invalid day! 🚫");
}
```

**Output:**
```
Wednesday 🗓️
```

</details>

---

## 🌟 Break and Continue Statements

- The **Break Statement** is used to exit a loop or switch statement.
- The **Continue Statement** skips the current iteration and moves to the next one in a loop.

<details>
<summary>Click to see Output</summary>

### ✅ Example 1: Break Statement

```javascript
for (let i = 0; i < 5; i++) {
  if (i === 3) {
    break;
  }
  console.log(i);
}
```

**Output:**
```
0
1
2
```

### ✅ Example 2: Continue Statement

```javascript
for (let i = 0; i < 5; i++) {
  if (i === 3) {
    continue;
  }
  console.log(i);
}
```

**Output:**
```
0
1
2
4
```

</details>

---

## 🔑 Summary

- **If Statement**: Executes code if the condition is true.
- **If-Else Statement**: Executes one block of code if the condition is true, otherwise, another block is executed.
- **If-Elif-Else Statement**: Checks multiple conditions in sequence.
- **Switch Statement**: Checks an expression and executes the corresponding case block.
- **Break Statement**: Exits a loop or switch statement.
- **Continue Statement**: Skips the current iteration of a loop and moves to the next one.

Happy coding! 🚀


#INTERVIEW QUESTION ON JAVASCRIPT CONTROL STATEMENTS 

### 1. **What is the difference between `if` and `else if` in JavaScript?**

**Answer:**
- `if` is used to check a condition, and if it's true, it executes the block of code.
- `else if` is used when you want to check additional conditions if the previous `if` statement(s) are false.

Example:
```javascript
let age = 20;
if (age < 18) {
  console.log("You are a minor.");
} else if (age >= 18 && age <= 60) {
  console.log("You are an adult.");
} else {
  console.log("You are a senior citizen.");
}
```

---

### 2. **What is the purpose of the `switch` statement in JavaScript?**

**Answer:**
The `switch` statement evaluates an expression and compares its value against multiple `case` options. It executes the block of code that matches the expression. If no match is found, the `default` block is executed (if provided).

Example:
```javascript
let day = 2;
switch (day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  case 3:
    console.log("Wednesday");
    break;
  default:
    console.log("Invalid day");
}
```

---

### 3. **How does the `break` statement work in loops and switch statements?**

**Answer:**
The `break` statement is used to exit a loop (such as `for`, `while`, etc.) or a `switch` statement before it completes all its iterations or checks.

Example (in a loop):
```javascript
for (let i = 0; i < 5; i++) {
  if (i === 3) {
    break;  // Exits the loop when i equals 3
  }
  console.log(i);
}
```
**Output:**
```
0
1
2
```

Example (in a `switch`):
```javascript
let fruit = "apple";
switch (fruit) {
  case "apple":
    console.log("Apple selected");
    break;
  case "banana":
    console.log("Banana selected");
    break;
}
```

---

### 4. **What is the purpose of the `continue` statement in loops?**

**Answer:**
The `continue` statement is used to skip the current iteration of a loop and continue to the next iteration.

Example:
```javascript
for (let i = 0; i < 5; i++) {
  if (i === 2) {
    continue;  // Skips the iteration when i equals 2
  }
  console.log(i);
}
```
**Output:**
```
0
1
3
4
```

---

### 5. **Explain the flow of an `if`, `else if`, and `else` chain.**

**Answer:**
An `if`, `else if`, and `else` chain checks multiple conditions in sequence. The first condition that evaluates to `true` will execute its corresponding block of code, and the rest will be skipped.

Example:
```javascript
let score = 75;
if (score >= 90) {
  console.log("Grade A");
} else if (score >= 70) {
  console.log("Grade B");
} else {
  console.log("Grade C");
}
```
**Output:**
```
Grade B
```

---

### 6. **Can you explain what happens when you use `switch` without `break`?**

**Answer:**
If you use `switch` without `break`, the code will continue to execute the following `case` statements (even if they don't match) until a `break` or the end of the `switch` block is reached. This is known as **fall-through** behavior.

Example:
```javascript
let fruit = "apple";
switch (fruit) {
  case "apple":
    console.log("Apple selected");
  case "banana":
    console.log("Banana selected");
    break;
  case "cherry":
    console.log("Cherry selected");
}
```
**Output:**
```
Apple selected
Banana selected
```

---

### 7. **How does the `else` block in an `if-else` statement work?**

**Answer:**
The `else` block executes when the condition in the `if` statement evaluates to `false`. If no `else` block is provided, nothing happens when the `if` condition is false.

Example:
```javascript
let temperature = 30;
if (temperature > 25) {
  console.log("It's hot outside! 🔥");
} else {
  console.log("The weather is cool. 🌬️");
}
```
**Output:**
```
It's hot outside! 🔥
```

---

### 8. **What is a nested `if` statement, and when would you use it?**

**Answer:**
A **nested `if` statement** is an `if` statement placed inside another `if` statement. You use it when you need to check multiple conditions that depend on each other.

Example:
```javascript
let age = 20;
let hasPermission = true;

if (age >= 18) {
  if (hasPermission) {
    console.log("Access granted.");
  } else {
    console.log("Permission required.");
  }
} else {
  console.log("You are too young.");
}
```
**Output:**
```
Access granted.
```

---

### 9. **What is the difference between a `for` loop and a `while` loop in JavaScript?**

**Answer:**
- A `for` loop is typically used when you know the number of iterations in advance. It contains initialization, condition, and increment/decrement all in one line.
- A `while` loop is used when the number of iterations is unknown and continues as long as the condition is true.

Example (`for` loop):
```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

Example (`while` loop):
```javascript
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```

---

### 10. **How does `switch` handle multiple cases for the same value?**

**Answer:**
In a `switch` statement, you can group multiple `case` blocks together for the same value without using `break` between them. This is useful when you want multiple conditions to execute the same block of code.

Example:
```javascript
let fruit = "apple";
switch (fruit) {
  case "apple":
  case "banana":
    console.log("Fruit is either apple or banana.");
    break;
  case "cherry":
    console.log("Fruit is cherry.");
    break;
}
```
**Output:**
```
Fruit is either apple or banana.
```

---

These interview questions and answers cover a wide range of **JavaScript control flow statements** such as `if`, `else if`, `else`, `switch`, `break`, and `continue`. They will help you demonstrate your understanding of conditional logic and loops in JavaScript.

# 🚀 JavaScript Pop-up Boxes & Functions

This document explains various **pop-up boxes** (like alert, confirm, and prompt) and **functions** in JavaScript with simple examples and outputs. The examples will help you understand how to use these features in your projects.

---

## 📣 **Alert Box**

An **alert box** is a simple popup that displays a message to the user and has an "OK" button. It is commonly used to display information or warnings.

<details>
<summary>Example 1: Simple Alert Box</summary>

```javascript
alert("Welcome to our website!");

```
# 🚀 JavaScript Pop-up Boxes & Functions

This document explains various **pop-up boxes** (like alert, confirm, and prompt) and **functions** in JavaScript with simple examples and outputs. The examples will help you understand how to use these features in your projects.

---

## 📣 **Alert Box**

An **alert box** is a simple popup that displays a message to the user and has an "OK" button. It is commonly used to display information or warnings.

<details>
<summary>Example 1: Simple Alert Box</summary>

```javascript
alert("Welcome to our website!");
```

**Output:**  
A popup appears with the message "Welcome to our website!" and an "OK" button.

</details>

<details>
<summary>Example 2: Alert for Form Submission</summary>

```javascript
function submitForm() {
  alert("Your form has been submitted!");
}
submitForm();
```

**Output:**  
A popup appears with the message "Your form has been submitted!" and an "OK" button.

</details>

---

## ✔️ **Confirm Box**

A **confirm box** is used to ask the user for confirmation. It provides "OK" and "Cancel" buttons, returning `true` if the user clicks "OK" and `false` if the user clicks "Cancel".

<details>
<summary>Example 1: Simple Confirm Box</summary>

```javascript
let result = confirm("Do you want to delete this item?");
if (result) {
  console.log("Item deleted.");
} else {
  console.log("Action canceled.");
}
```

**Output:**  
A popup appears with the message "Do you want to delete this item?" and "OK" and "Cancel" buttons.  
The console will log "Item deleted." or "Action canceled." depending on the user's choice.

</details>

<details>
<summary>Example 2: Confirm Box for Navigation</summary>

```javascript
let navigate = confirm("Are you sure you want to leave this page?");
if (navigate) {
  window.location.href = "https://www.example.com";
} else {
  console.log("Staying on the page.");
}
```

**Output:**  
A popup appears asking "Are you sure you want to leave this page?" and depending on the user's choice, the page either navigates or stays.

</details>

---

## ✍️ **Prompt Box**

A **prompt box** asks the user for input and returns the value entered by the user in a text field.

<details>
<summary>Example 1: Simple Prompt Box</summary>

```javascript
let userName = prompt("Please enter your name:");
console.log("Hello, " + userName);
```

**Output:**  
A prompt box asks the user to enter their name. The console will display "Hello, [name]" after the user enters the name.

</details>

<details>
<summary>Example 2: Prompt Box for Age</summary>

```javascript
let age = prompt("How old are you?");
console.log("You are " + age + " years old.");
```

**Output:**  
A prompt box asks the user "How old are you?". The console will display "You are [age] years old." after the user enters their age.

</details>

---

## 🛠️ **Functions in JavaScript**

A **function** in JavaScript is a block of code that performs a specific task. Functions can take inputs (parameters) and return values.

<details>
<summary>Example 1: Simple Function</summary>

```javascript
function greet() {
  console.log("Hello, World!");
}
greet();
```

**Output:**  
```
Hello, World!
```

</details>

<details>
<summary>Example 2: Function with Return Value</summary>

```javascript
function add(a, b) {
  return a + b;
}
let result = add(3, 4);
console.log(result);
```

**Output:**  
```
7
```

</details>

---

## 🎯 **Functions with Parameters**

Functions with **parameters** allow you to pass values into the function for processing. These values can be used to perform calculations or customize the function’s behavior.

<details>
<summary>Example 1: Function with One Parameter</summary>

```javascript
function greet(name) {
  console.log("Hello, " + name + "!");
}
greet("John");
```

**Output:**  
```
Hello, John!
```

</details>

<details>
<summary>Example 2: Function with Multiple Parameters</summary>

```javascript
function multiply(a, b) {
  return a * b;
}
let result = multiply(5, 3);
console.log(result);
```

**Output:**  
```
15
```

</details>

---

## 🔁 **Function with Return Value**

A **function with return** takes input, processes it, and returns a result. The `return` keyword is used to send the value back to the calling code.

<details>
<summary>Example 1: Function with Return</summary>

```javascript
function greet(name) {
  return "Hello, " + name + "!";
}
let message = greet("Alice");
console.log(message);
```

**Output:**  
```
Hello, Alice!
```

</details>

<details>
<summary>Example 2: Function with Return for Calculation</summary>

```javascript
function subtract(a, b) {
  return a - b;
}
let result = subtract(10, 5);
console.log(result);
```

**Output:**  
```
5
```

</details>

---

## 📚 **Summary**

- **Alert Box (`alert`)**: Displays a simple message to the user.
- **Confirm Box (`confirm`)**: Asks for user confirmation with "OK" and "Cancel".
- **Prompt Box (`prompt`)**: Asks for user input and returns the entered value.
- **Functions**: A block of code that performs a specific task. Functions can have parameters and return values.
- **Functions with Parameters**: Functions that accept inputs to customize their behavior.
- **Functions with Return**: Functions that process input and return a result.

These JavaScript features are essential for creating interactive web applications and are commonly used in many coding tasks.

---

Enjoy learning JavaScript! 😄
```

### Explanation:

- **Alert Box**: Used to display simple messages to users.
- **Confirm Box**: Used for obtaining user confirmation.
- **Prompt Box**: Used to ask users for input.
- **Functions**: Basic code blocks that can take parameters and return values.
- **Functions with Parameters**: Functions that work with dynamic inputs.
- **Functions with Return**: Functions that calculate and return a value.

Each section has examples and outputs enclosed in **`<details>`** and **`<summary>`** tags for easy display and toggling of content. The use of emojis makes the file more engaging and easy to read!


```

# 🚀 JavaScript Events

This document explains **JavaScript events**—a powerful feature for creating interactive web applications. It includes examples of different event types and how to handle them in JavaScript.

---

## 📝 **What Are Events?**

In JavaScript, **events** are actions that can be triggered by the user or the browser. These can be actions like clicking a button, hovering over an element, submitting a form, or even loading a page. JavaScript can **listen** for these events and respond with a function (called an **event handler**).

---

## 🌟 **Types of Events in JavaScript**

- **Click Event**: Triggered when the user clicks on an element.
- **Mouse Events**: Triggered when the user interacts with the mouse, like `mouseover`, `mouseout`, and `mousemove`.
- **Keyboard Events**: Triggered by user keystrokes like `keydown`, `keyup`, and `keypress`.
- **Form Events**: Triggered when forms are interacted with, like `submit`, `change`, and `input`.
- **Window Events**: Triggered by actions like resizing the window or loading a page.

---

## 🎯 **Examples of JavaScript Events**

### 1. **Click Event**

A **click event** is triggered when an element (like a button) is clicked.

<details>
<summary>Example: Click Event</summary>

```javascript
document.getElementById("myButton").addEventListener("click", function() {
  alert("Button clicked!");
});

