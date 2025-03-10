# Introduction to Javascript

Relevant reading:
- https://javascript.info/intro
- https://javascript.info/manuals-specifications
- https://javascript.info/code-editors
- https://javascript.info/devtools
- https://javascript.info/coding-style
- https://javascript.info/comments
- https://javascript.info/ninja-code
## 1. Getting Started with JavaScript

### Exercise 1: Using the Developer Console
1. Open your web browser's Developer Console.
2. Type `console.log("Hello, JavaScript!");` and press Enter.
3. Observe the output.

### Exercise 2: Running JavaScript in Node.js
1. Install Node.js from [nodejs.org](https://nodejs.org/).
2. Open a terminal and type `node` to start an interactive session.
3. Enter `console.log("Welcome to JavaScript in Node.js!");` and observe the output.

---

## 2. Lexical Structure

### Exercise 3: Case Sensitivity
1. Create a JavaScript file and define two variables:
   ```js
   let myVar = 10;
   let MyVar = 20;
   console.log(myVar, MyVar);
   ```
2. Run the script and observe the output.
3. What happens if you try to use `MYVAR`?

### Exercise 4: Comments
1. Write a single-line comment explaining the purpose of the following code:
   ```js
   // This line prints a greeting message
   console.log("Hello, world!");
   ```
2. Write a multi-line comment explaining the following function:
   ```js
   /*
    * This function adds two numbers and returns the result.
    */
   function add(a, b) {
       return a + b;
   }
   ```

### Exercise 5: Literals
1. Declare and print different types of literals:
   ```js
   console.log(42);       // Number literal
   console.log("Hello");  // String literal
   console.log(true);      // Boolean literal
   console.log(null);      // Null literal
   ```

---

## 3. Identifiers and Reserved Words

### Exercise 6: Identifiers
1. Declare variables using valid JavaScript identifiers:
   ```js
   let myVariable = 10;
   let _underscore = 20;
   let $dollarSign = 30;
   console.log(myVariable, _underscore, $dollarSign);
   ```
2. Try using an invalid identifier (e.g., `let 1stVariable = 100;`). What happens?

### Exercise 7: Reserved Words
1. Try declaring a variable using a reserved word (e.g., `let function = 10;`).
2. Observe the error message.

---

## 4. Semicolons and Formatting

### Exercise 8: Optional Semicolons
1. Write and execute the following code:
   ```js
   let a = 5
   let b = 10
   console.log(a + b)
   ```
2. Add semicolons explicitly and compare the readability.

---

## 5. Basic JavaScript Syntax

### Exercise 9: Variable Declarations
1. Declare variables using `var`, `let`, and `const`.
2. Modify `let` and `const` variables to see what happens.
   ```js
   var x = 10;
   let y = 20;
   const z = 30;
   console.log(x, y, z);
   y = 25;
   console.log(y);
   // Try modifying z and observe the error
   ```

### Exercise 10: Basic Arithmetic Operations
1. Perform arithmetic operations using `+`, `-`, `*`, `/`, and `%`.
   ```js
   let num1 = 10;
   let num2 = 3;
   console.log(num1 + num2);
   console.log(num1 - num2);
   console.log(num1 * num2);
   console.log(num1 / num2);
   console.log(num1 % num2);
   ```



