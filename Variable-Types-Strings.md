# JavaScript Fundamentals: Exercises for Students

## Types and Values

### Basic Exercises:
1. Declare a variable and assign a number to it. Then print the type of the variable using `typeof`.
   ```javascript
   let num = 42;
   console.log(typeof num);  // Expected output: 'number'
   ```

### Challenge Exercises:
2. Declare variables with different types (string, number, boolean, array, object) and log their types.
   ```javascript
   // Your code here
   ```

3. Create a variable that changes type during program execution. Log the type before and after.
   ```javascript
   // Your code here
   ```

## Variables

### Basic Exercises:
1. Create two variables `a` and `b`. Assign values to them and print the result of their addition.
   ```javascript
   let a = 5;
   let b = 10;
   console.log(a + b);  // Expected output: 15
   ```

2. Declare variables using `var`, `let`, and `const`. Explain the difference in comments.
   ```javascript
   // Your code here
   ```

3. Create a variable in the global scope and another in a function scope. Demonstrate scope differences.
   ```javascript
   // Your code here
   ```

### Challenge Exercises:
4. Create a variable using `let` inside a block scope. Try to access it outside the block and explain the result.
   ```javascript
   // Your code here
   ```

5. Demonstrate variable hoisting with `var` vs `let`.
   ```javascript
   // Your code here
   ```

## `use strict` Directive

### Basic Exercises:
1. Write a function with a `use strict` directive and try declaring a variable without `var`, `let`, or `const`. Observe the error.
   ```javascript
   "use strict";
   function test() {
     x = 10;  // Error: 'x' is not defined
   }
   test();
   ```

2. Compare the behavior of undeclared variables with and without strict mode.
   ```javascript
   // Your code here
   ```
   
## Primitive Types

### Basic Exercises:
1. Create variables of different primitive types (string, number, boolean, null, undefined) and log their types.
   ```javascript
   let str = "hello";
   let num = 10;
   let bool = true;
   let nothing = null;
   let undef;

   console.log(typeof str);      // string
   console.log(typeof num);      // number
   console.log(typeof bool);     // boolean
   console.log(typeof nothing);  // object (null is a special case)
   console.log(typeof undef);    // undefined
   ```

2. Demonstrate type coercion by mixing different primitive types in operations.
   ```javascript
   // Your code here
   ```

### Challenge Exercises:
3. Write code that demonstrates the difference between `==` and `===` with primitives.
   ```javascript
   // Your code here
   ```

## Object Types

### Basic Exercises:
1. Create an object with properties `name`, `age`, and `city`. Print the object.
   ```javascript
   let person = { name: "John", age: 30, city: "New York" };
   console.log(person);
   ```

2. Add a method to an object and call it.
   ```javascript
   // Your code here
   ```

3. Access object properties using both dot notation and bracket notation.
   ```javascript
   // Your code here
   ```

### Challenge Exercises:
4. Create a nested object structure and access a deeply nested property.
   ```javascript
   // Your code here
   ```

## Immutable vs Mutable Types

### Basic Exercises:
1. Assign a string value to a variable, then try to change the first character of the string.
   ```javascript
   let str = "hello";
   str[0] = 'H';  // Does not change the string
   console.log(str);  // 'hello'
   ```

2. Create an array and modify its elements.
   ```javascript
   let arr = [1, 2, 3];
   arr[0] = 10;
   console.log(arr);  // [10, 2, 3]
   ```


## Numbers

### Basic Exercises:
1. Declare two integer variables and add them together.
   ```javascript
   let int1 = 25;
   let int2 = 75;
   console.log(int1 + int2);  // 100
   ```

2. Create a floating-point number and perform an operation that results in a floating-point number.
   ```javascript
   let floatNum = 10.5;
   console.log(floatNum * 2);  // 21
   ```

3. Use the `Math` object to calculate the square root of 16.
   ```javascript
   console.log(Math.sqrt(16));  // 4
   ```


## Number Limitations

### Basic Exercises:
1. Create a number that exceeds the maximum safe integer value and observe the result.
   ```javascript
   let overflow1 = Number.MAX_SAFE_INTEGER + 1;
   let overflow2 = Number.MAX_SAFE_INTEGER + 2;
   console.log(overflow1 === overflow2);  // true
   ```

2. Divide a number by zero and check the result.
   ```javascript
   let result = 10 / 0;
   console.log(result);  // Infinity
   ```


## Number Conversion

### Basic Exercises:
1. Use `parseInt` to convert a string to an integer.
   ```javascript
   let str = "100";
   let num = parseInt(str);
   console.log(num);  // 100
   ```

2. Use `parseFloat` to convert a string to a floating-point number.
   ```javascript
   let str = "10.99";
   let floatNum = parseFloat(str);
   console.log(floatNum);  // 10.99
   ```

### Challenge Exercises:
3. Demonstrate the limitations of number parsing with unexpected inputs.
   ```javascript
   // Your code here
   ```

## BigInt

### Basic Exercises:
1. Use `BigInt` to store a large integer number.
   ```javascript
   let bigNum = BigInt("123456789012345678901234567890");
   console.log(bigNum);
   
   // Alternative syntax
   let bigNum2 = 123456789012345678901234567890n;
   console.log(bigNum2);
   ```

2. Perform arithmetic operations with BigInt values.
   ```javascript
   // Your code here
   ```

### Challenge Exercises:
3. Compare BigInt with regular Number and demonstrate when BigInt is necessary.
   ```javascript
   // Your code here
   ```


## String Basics

### Basic Exercises:
1. Create a string using a string literal and log it.
   ```javascript
   let str = 'Hello, world!';
   console.log(str);  // Hello, world!
   ```

2. Use escape sequences to print a string with quotes.
   ```javascript
   let quote = "He said, \"Hello!\"";
   console.log(quote);  // He said, "Hello!"
   ```

### Challenge Exercises:
3. Demonstrate the difference between single quotes, double quotes, and backticks.
   ```javascript
   // Your code here
   ```

4. Create a multiline string using both escape sequences and template literals.
   ```javascript
   // Your code here
   ```

## String Operations

### Basic Exercises:
1. Use `toUpperCase` to convert a string to uppercase.
   ```javascript
   let str = "hello";
   console.log(str.toUpperCase());  // HELLO
   ```

2. Concatenate two strings and log the result.
   ```javascript
   let str1 = "Hello, ";
   let str2 = "world!";
   console.log(str1 + str2);  // Hello, world!
   ```

3. Find the length of a string and use the `charAt` method to access a character.
   ```javascript
   let str = "JavaScript";
   console.log(str.length);      // 10
   console.log(str.charAt(0));   // J
   ```

### Challenge Exercises:
4. Find all occurrences of a substring within a string.
   ```javascript
   // Your code here
   ```

5. Create a function that reverses a string without using the built-in reverse() method.
   ```javascript
   // Your code here
   ```

## Template Literals

### Basic Exercises:
1. Use template literals to create a sentence with variables.
   ```javascript
   let name = "Alice";
   let age = 25;
   console.log(`My name is ${name} and I am ${age} years old.`);
   ```

2. Create a multiline string using template literals.
   ```javascript
   // Your code here
   ```

### Challenge Exercises:
3. Use template literals with expressions and function calls.
   ```javascript
   // Your code here
   ```

4. Create a tagged template function that formats strings in a special way.
   ```javascript
   // Your code here
   ```

## Special Values

### Basic Exercises:
1. Create a variable with the value `null` and log it.
   ```javascript
   let value = null;
   console.log(value);  // null
   ```

2. Create a variable without assigning a value to it and log it.
   ```javascript
   let value;
   console.log(value);  // undefined
   ```

3. Divide zero by zero and check if the result is `NaN`.
   ```javascript
   let result = 0 / 0;
   console.log(result);          // NaN
   console.log(isNaN(result));   // true
   ```



## Comparison Operators

### Basic Exercises:
1. Use comparison operators (`>`, `<`, `==`, `!=`) to compare two values.
   ```javascript
   let a = 5;
   let b = 10;
   console.log(a < b);   // true
   console.log(a == b);  // false
   ```

2. Compare values of different types using `==` vs `===`.
   ```javascript
   // Your code here
   ```

## Global Object

### Basic Exercises:
1. Access a global object property (`window` in browsers or `global` in Node.js) and log it.
   ```javascript
   // In a browser
   console.log(window.location);
   
   // In Node.js
   console.log(global.process);
   ```

2. Add a property to the global object and access it from different scopes.
   ```javascript
   // Your code here
   ```

### Challenge Exercises:
3. Demonstrate how to avoid polluting the global namespace in your code.
   ```javascript
   // Your code here
   ```

4. Show how to check if code is running in a browser vs Node.js environment.
   ```javascript
   // Your code here
   ```



---

## Instructions for Students

1. Work through each exercise progressively, starting with basic exercises before moving to challenges.
2. Write your code in the provided spaces or in separate JavaScript files.
3. Test your code in a browser console or Node.js environment.
4. Try to predict the output before running the code.
5. For each challenge exercise, write a brief explanation of what your code demonstrates.
