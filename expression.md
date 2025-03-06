# JavaScript Exercises: Expressions and Operators

## Basic Expressions

### Fundamentals
1. Write expressions that evaluate to each of the following types:
   - A number
   - A string
   - A boolean
   - `null`
   - `undefined`

   ```javascript
   let num = 42;
   let str = "Hello";
   let bool = true;
   let nothing = null;
   let notDefined;
   console.log(num, str, bool, nothing, notDefined);
   ```

## Primary Expressions

### Simple Values
1. Evaluate and print various primary expressions:
   ```javascript
   console.log(3.14);
   console.log("JavaScript");
   let x = 5;
   console.log(x);
   ```

## Object and Array Expressions

### Object Literals
1. Create an object using object literal notation:
   ```javascript
   let person = { name: "Alice", age: 25 };
   console.log(person);
   ```

### Array Literals
1. Create an array using array literal notation:
   ```javascript
   let numbers = [1, 2, 3, 4, 5];
   console.log(numbers);
   ```

2. Create a multi-dimensional array:
   ```javascript
   // Your code here
   ```

3. Create an array with mixed data types and sparse elements:
   ```javascript
   // Your code here
   ```

## Function Expressions

### Function Definition Expressions
1. Create a function using a function expression:
   ```javascript
   const greet = function(name) {
       return `Hello, ${name}!`;
   };
   console.log(greet("Bob"));
   ```

2. Create a function expression with multiple parameters and store it in a variable:
   ```javascript
   // Your code here
   ```

### Arrow Function Expressions
1. Create a simple arrow function:
   ```javascript
   const square = (x) => x * x;
   console.log(square(4));
   ```

2. Write arrow functions with and without curly braces, demonstrating the difference:
   ```javascript
   // Your code here
   ```

## Property Access Expressions

### Dot Notation
1. Access object properties using dot notation:
   ```javascript
   let obj = {a: 10, b: 20};
   console.log(obj.a);
   ```

2. Access nested properties using dot notation:
   ```javascript
   // Your code here
   ```

### Bracket Notation
1. Access object properties using bracket notation:
   ```javascript
   let obj = {a: 10, b: 20};
   console.log(obj["b"]);
   ```

2. Use variables as property names with bracket notation:
   ```javascript
   // Your code here
   ```

### Optional Chaining
1. Use optional chaining to safely access potentially undefined properties:
   ```javascript
   let user = null;
   console.log(user?.name);
   ```

2. Compare optional chaining with traditional approaches:
   ```javascript
   // Your code here
   ```

## Invocation Expressions

### Function Calls
1. Call a function and capture its return value:
   ```javascript
   function add(a, b) {
       return a + b;
   }
   console.log(add(3, 5));
   ```

2. Call a function with too many or too few arguments:
   ```javascript
   // Your code here
   ```

### Constructor Invocation
1. Create objects using constructor invocation:
   ```javascript
   let date = new Date();
   console.log(date);
   ```

## Arithmetic Expressions

### Basic Arithmetic
1. Perform basic arithmetic operations:
   ```javascript
   console.log(10 + 5);  // Addition
   console.log(10 - 5);  // Subtraction
   console.log(10 * 5);  // Multiplication
   console.log(10 / 5);  // Division
   console.log(10 % 3);  // Remainder
   ```

2. Demonstrate exponentiation and complex calculations:
   ```javascript
   // Your code here
   ```

3. Show edge cases in arithmetic operations (infinity, NaN):
   ```javascript
   // Your code here
   ```

### Operator Precedence
1. Demonstrate operator precedence in expressions:
   ```javascript
   console.log(2 + 3 * 4);
   console.log((2 + 3) * 4);
   ```

### Operator Associativity
1. Explain how Operator Precedence and Associativity are dominating how the code below works:
   ```javascript
   let x = 5;
   x *= 2 + 3;
   console.log(x);
   ```


## Increment and Decrement

### Prefix and Postfix Operators
1. Demonstrate prefix and postfix increment and decrement:
   ```javascript
   let a = 5;
   console.log(a++);  // Postfix increment: returns 5, then a becomes 6
   console.log(++a);  // Prefix increment: a becomes 7, then returns 7
   console.log(a--);  // Postfix decrement: returns 7, then a becomes 6
   console.log(--a);  // Prefix decrement: a becomes 5, then returns 5
   ```

## Bitwise Operators

### Binary Operations
1. Perform bitwise operations on integers:
   ```javascript
   console.log(5 & 3);   // AND
   console.log(5 | 3);   // OR
   console.log(5 ^ 3);   // XOR
   console.log(~5);      // NOT
   console.log(5 << 1);  // Left shift
   console.log(5 >> 1);  // Right shift
   ```

## Comparison Operators

### Equality and Relational
1. Compare values using different comparison operators:
   ```javascript
   console.log(5 > 3);     // Greater than
   console.log(5 < 3);     // Less than
   console.log(5 == "5");  // Equal (with type coercion)
   console.log(5 === "5"); // Strictly equal (no type coercion)
   console.log(5 != 3);    // Not equal
   ```

3. Compare objects, arrays, and complex data types:
   ```javascript
   // Your code here
   ```

### Special Operators
1. Use the `in` operator to check for property existence:
   ```javascript
   let obj = { name: "Alice", age: 25 };
   console.log("name" in obj);    // true
   console.log("salary" in obj);  // false
   ```

2. Use the `instanceof` operator to check object types:
   ```javascript
   console.log([] instanceof Array);   // true
   console.log({} instanceof Object);  // true
   ```

## Logical Operators

### Basic Logic
1. Perform logical operations:
   ```javascript
   console.log(true && false);  // Logical AND
   console.log(true && true);   // Logical AND
   console.log(false || true);  // Logical OR
   console.log(false || false); // Logical OR
   console.log(!true);          // Logical NOT
   console.log(!false);         // Logical NOT
   ```

2. Combine multiple logical operators in complex conditions:
   ```javascript
   // Your code here
   ```

### Short-Circuit Evaluation
1. Demonstrate short-circuit evaluation in logical operators:
   ```javascript
   console.log(null && "Hello");  // null (short-circuits)
   console.log("Hi" || "Hello");  // "Hi" (short-circuits)
   ```


### Nullish Coalescing
1. Use the nullish coalescing operator to provide defaults:
   ```javascript
   let val = null;
   console.log(val ?? "Default Value");  // "Default Value"
   ```

2. Compare nullish coalescing (`??`) with logical OR (`||`):
   ```javascript
   // Your code here
   ```

## Assignment Operators

### Basic Assignment
1. Use various assignment operators:
   ```javascript
   let b = 10;
   b += 5;  // Addition assignment
   console.log(b);
   ```

2. Chain multiple assignments:
   ```javascript
   // Your code here
   ```

### Compound Assignment
1. Use compound assignment operators with different operations:
   ```javascript
   // Your code here (+=, -=, *=, /=, %=, etc.)
   ```


## Conditional Operators

### Ternary Operator
1. Use the ternary conditional operator:
   ```javascript
   let age = 20;
   let status = age >= 18 ? "Adult" : "Minor";
   console.log(status);
   ```

3. Translate code above to a if-else statement:
   ```javascript
   // Your code here
   ```

## Unary Operators

### Type Operators
1. Use the `typeof` operator to determine data types:
   ```javascript
   console.log(typeof 42);      // "number"
   console.log(typeof "hello"); // "string"
   console.log(typeof true);    // "boolean"
   ```


### Other Unary Operators
1. Use the `delete` operator to remove object properties:
   ```javascript
   let obj = { name: "Alice", age: 25 };
   delete obj.age;
   console.log(obj);  // { name: "Alice" }
   ```




## Advanced Expression Patterns

### Complex Expressions
1. Build a complex expression with multiple operators:
   ```javascript
   let result = (3 + 5) * 2 - 4 / 2;
   console.log(result);  // 14
   ```


## Operator Behavior

### Operator Overloading
1. Observe JavaScript's implicit operator behavior:
   ```javascript
   console.log("5" + 5);   // "55" (string concatenation)
   console.log("5" - 5);   // 0 (numeric subtraction)
   console.log("5" * 2);   // 10 (numeric multiplication)
   ```

2. Create examples that demonstrate unexpected operator behavior:
   ```javascript
   // Your code here
   ```

---

## Instructions for Students

1. Complete each exercise by writing code in the provided spaces.
2. For exercises without sample code, develop your own solution based on the description.
3. Test your code in a browser console or Node.js environment.
4. Pay attention to operator precedence and associativity when solving complex expressions.
5. Try to predict the output before running your code.
6. Experiment with variations of the exercises to deepen your understanding.
