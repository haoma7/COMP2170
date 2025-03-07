## 1. Modules in Node.js

### Exercise 1.1
Create two files: `mathUtils.js` and `app.js`. In `mathUtils.js`, create and export functions for `add`, `subtract`, `multiply`, and `divide`. In `app.js`, import these functions and use them.

**mathUtils.js**
```javascript
// Your code here
```

**app.js**
```javascript
// Your code here
```

**Expected Answer:**

**mathUtils.js**
```javascript
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

function multiply(a, b) {
  return a * b;
}

function divide(a, b) {
  if (b === 0) {
    throw new Error("Cannot divide by zero");
  }
  return a / b;
}

module.exports = {
  add,
  subtract,
  multiply,
  divide
};
```

**app.js**
```javascript
const mathUtils = require('./mathUtils');

console.log(mathUtils.add(5, 3));      // 8
console.log(mathUtils.subtract(5, 3)); // 2
console.log(mathUtils.multiply(5, 3)); // 15
console.log(mathUtils.divide(6, 3));   // 2
```

### Exercise 1.2
Create a Node.js module for a `Logger` class that can log messages with different severity levels (info, warning, error). Export the class and use it in another file.

**logger.js**
```javascript
// Your code here
```

**logTest.js**
```javascript
// Your code here
```

**Expected Answer:**

**logger.js**
```javascript
class Logger {
  constructor(name) {
    this.name = name;
  }
  
  info(message) {
    console.log(`[INFO] ${this.name}: ${message}`);
  }
  
  warning(message) {
    console.log(`[WARNING] ${this.name}: ${message}`);
  }
  
  error(message) {
    console.error(`[ERROR] ${this.name}: ${message}`);
  }
}

module.exports = Logger;
```

**logTest.js**
```javascript
const Logger = require('./logger');

const appLogger = new Logger('AppService');
const dbLogger = new Logger('Database');

appLogger.info('Application started');
dbLogger.info('Connected to database');
appLogger.warning('High memory usage');
dbLogger.error('Connection failed');

/* Output:
[INFO] AppService: Application started
[INFO] Database: Connected to database
[WARNING] AppService: High memory usage
[ERROR] Database: Connection failed
*/
```

## 2. `exports` vs `module.exports`

### Exercise 2.1
What's the difference between `exports` and `module.exports`? Demonstrate with code examples where using one over the other makes a difference.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
// file1.js - Using exports directly (works as expected)
exports.name = "Module 1";
exports.sayHello = function() {
  return `Hello from ${this.name}`;
};

// file2.js - Reassigning exports (doesn't work!)
exports = {
  name: "Module 2",
  sayHello: function() {
    return `Hello from ${this.name}`;
  }
};
// This won't export anything! The local exports variable is reassigned but module.exports remains unchanged

// file3.js - Using module.exports (works as expected)
module.exports = {
  name: "Module 3",
  sayHello: function() {
    return `Hello from ${this.name}`;
  }
};

// app.js - Testing the imports
const mod1 = require('./file1');
console.log(mod1.sayHello()); // "Hello from Module 1"

const mod2 = require('./file2');
console.log(mod2); // {} - empty object, nothing was exported!

const mod3 = require('./file3');
console.log(mod3.sayHello()); // "Hello from Module 3"

/*
Explanation:
- exports is just a reference to module.exports
- When you add properties to exports, they get added to module.exports
- If you reassign exports, you break the reference to module.exports
- module.exports is what actually gets returned from require()
*/
```

### Exercise 2.2
Create a module that exports a function as its main functionality. Then modify it to export both the main function and some utility functions. Use appropriate export style for each case.

**calculator.js (Version 1)**
```javascript
// Your code here
```

**calculator.js (Version 2)**
```javascript
// Your code here
```

**app.js**
```javascript
// Your code here
```

**Expected Answer:**

**calculator.js (Version 1)**
```javascript
// Export a single function as the main export
module.exports = function calculator(a, b, operation) {
  switch(operation) {
    case 'add': return a + b;
    case 'subtract': return a - b;
    case 'multiply': return a * b;
    case 'divide': return b !== 0 ? a / b : null;
    default: return null;
  }
};
```

**calculator.js (Version 2)**
```javascript
// Main function
function calculator(a, b, operation) {
  switch(operation) {
    case 'add': return add(a, b);
    case 'subtract': return subtract(a, b);
    case 'multiply': return multiply(a, b);
    case 'divide': return divide(a, b);
    default: return null;
  }
}

// Utility functions
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

function multiply(a, b) {
  return a * b;
}

function divide(a, b) {
  return b !== 0 ? a / b : null;
}

// Export main function as default and utilities as named exports
module.exports = calculator;
module.exports.add = add;
module.exports.subtract = subtract;
module.exports.multiply = multiply;
module.exports.divide = divide;
```

**app.js**
```javascript
// Using Version 1
const calc1 = require('./calculator-v1');
console.log(calc1(5, 3, 'add')); // 8

// Using Version 2
const calc2 = require('./calculator-v2');
console.log(calc2(5, 3, 'multiply')); // 15
// Also can use the utility functions directly
console.log(calc2.add(10, 20)); // 30
```

## 3. ES Modules (ESM) in ES6

### Exercise 3.1
Create two ES6 modules: one that exports multiple functions (named exports) and another that imports and uses these functions.

**mathFunctions.js**
```javascript
// Your code here
```

**app.js**
```javascript
// Your code here
```

**Expected Answer:**

**mathFunctions.js**
```javascript
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}

export function multiply(a, b) {
  return a * b;
}

export function divide(a, b) {
  if (b === 0) {
    throw new Error("Cannot divide by zero");
  }
  return a / b;
}
```

**app.js**
```javascript
import { add, subtract, multiply, divide } from './mathFunctions.js';

console.log(add(10, 5));      // 15
console.log(subtract(10, 5)); // 5
console.log(multiply(10, 5)); // 50
console.log(divide(10, 5));   // 2
```

### Exercise 3.2
Create an ES6 module that has both a default export and named exports. Then import both in another file.

**userModule.js**
```javascript
// Your code here
```

**app.js**
```javascript
// Your code here
```

**Expected Answer:**

**userModule.js**
```javascript
// Class as default export
export default class User {
  constructor(name, email) {
    this.name = name;
    this.email = email;
  }
  
  getInfo() {
    return `${this.name} (${this.email})`;
  }
}

// Named exports
export function validateEmail(email) {
  const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return regex.test(email);
}

export function formatName(name) {
  return name.trim().toLowerCase().replace(/\b\w/g, c => c.toUpperCase());
}
```

**app.js**
```javascript
import User, { validateEmail, formatName } from './userModule.js';

// Using default export
const user = new User('john doe', 'john@example.com');
console.log(user.getInfo()); // "John Doe (john@example.com)"

// Using named exports
console.log(validateEmail('invalid-email')); // false
console.log(validateEmail('valid@example.com')); // true
console.log(formatName('alice SMITH')); // "Alice Smith"
```

