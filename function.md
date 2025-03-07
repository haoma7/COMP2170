# JavaScript Functions Exercises

## 1. Function Declaration

### Exercise 1.1
Create a function declaration named `calculateArea` that takes two parameters: `length` and `width`. The function should calculate and return the area of a rectangle.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function calculateArea(length, width) {
  return length * width;
}

// Example usage
console.log(calculateArea(5, 3)); // Output: 15
```

### Exercise 1.2
Write a function declaration called `isPalindrome` that checks if a string is a palindrome (reads the same forward and backward). The function should return `true` if the string is a palindrome and `false` otherwise.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function isPalindrome(str) {
  // Remove non-alphanumeric characters and convert to lowercase
  const cleanStr = str.toLowerCase().replace(/[^a-z0-9]/g, '');
  // Reverse the string and compare
  const reversedStr = cleanStr.split('').reverse().join('');
  return cleanStr === reversedStr;
}

// Example usage
console.log(isPalindrome("A man, a plan, a canal: Panama")); // Output: true
console.log(isPalindrome("hello")); // Output: false
```

## 2. Function Expression

### Exercise 2.1
Create a function expression assigned to a variable named `getFullName` that takes two parameters: `firstName` and `lastName`. The function should concatenate and return the full name.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
const getFullName = function(firstName, lastName) {
  return `${firstName} ${lastName}`;
};

// Example usage
console.log(getFullName("John", "Doe")); // Output: "John Doe"
```

### Exercise 2.2
Write a function expression assigned to a variable named `countVowels` that counts the number of vowels in a string.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
const countVowels = function(str) {
  const vowels = ['a', 'e', 'i', 'o', 'u'];
  let count = 0;
  
  for (let char of str.toLowerCase()) {
    if (vowels.includes(char)) {
      count++;
    }
  }
  
  return count;
};

// Example usage
console.log(countVowels("JavaScript")); // Output: 3
```

## 3. Function Declaration vs Function Expression

### Exercise 3.1
Explain the differences between function declarations and function expressions by writing one of each that calculates the factorial of a number. Then, demonstrate hoisting by calling each function before its definition.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
// This will work because function declarations are hoisted
console.log(factorialDeclaration(5)); // Output: 120

// This will throw an error because function expressions are not hoisted
// console.log(factorialExpression(5)); // Error: factorialExpression is not a function

// Function declaration
function factorialDeclaration(n) {
  if (n <= 1) return 1;
  return n * factorialDeclaration(n - 1);
}

// Function expression
const factorialExpression = function(n) {
  if (n <= 1) return 1;
  return n * factorialExpression(n - 1);
};

// This works now that the function expression is defined
console.log(factorialExpression(5)); // Output: 120
```

### Exercise 3.2
Create a scenario where you need to use both a function declaration and a function expression. Explain why you chose each for their specific role.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
// Function declaration for a utility that will be used throughout the code
function formatCurrency(amount) {
  return `$${amount.toFixed(2)}`;
}

// Using a function expression for an event handler
const button = document.getElementById('calculate-button'); // Assuming this exists in HTML
const calculateTotal = function(event) {
  const subtotal = 19.99;
  const tax = subtotal * 0.08;
  const total = subtotal + tax;
  alert(`Your total is: ${formatCurrency(total)}`);
};

// Attaching the event handler
if (button) {
  button.addEventListener('click', calculateTotal);
}

/* 
Explanation:
- formatCurrency is a function declaration because it's a utility function that might be used 
  in multiple places and benefits from hoisting.
- calculateTotal is a function expression because it's used as a callback for an event, 
  and keeping it as a named variable makes the code more readable and maintainable.
*/
```

## 4. Optional Parameters and Defaults

### Exercise 4.1
Create a function named `createGreeting` that takes a name parameter and an optional greeting parameter with a default value of "Hello". The function should return the greeting followed by the name.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function createGreeting(name, greeting = "Hello") {
  return `${greeting}, ${name}!`;
}

// Example usage
console.log(createGreeting("Alice")); // Output: "Hello, Alice!"
console.log(createGreeting("Bob", "Hi")); // Output: "Hi, Bob!"
```

### Exercise 4.2
Write a function named `calculateDiscount` that calculates the final price after a discount. It should take parameters for the original price, discount percentage (default 10%), and whether the customer is a premium member (default false). Premium members get an additional 5% off.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function calculateDiscount(originalPrice, discountPercentage = 10, isPremiumMember = false) {
  let discount = discountPercentage;
  
  if (isPremiumMember) {
    discount += 5;
  }
  
  const discountAmount = originalPrice * (discount / 100);
  return originalPrice - discountAmount;
}

// Example usage
console.log(calculateDiscount(100)); // Output: 90 (10% discount)
console.log(calculateDiscount(100, 20)); // Output: 80 (20% discount)
console.log(calculateDiscount(100, 10, true)); // Output: 85 (15% discount for premium member)
```

## 5. Functions as Methods

### Exercise 5.1
Create an object named `calculator` with methods for `add`, `subtract`, `multiply`, and `divide`. Each method should take two parameters and return the result of the operation.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
const calculator = {
  add: function(a, b) {
    return a + b;
  },
  subtract: function(a, b) {
    return a - b;
  },
  multiply: function(a, b) {
    return a * b;
  },
  divide: function(a, b) {
    if (b === 0) {
      return "Cannot divide by zero";
    }
    return a / b;
  }
};

// Example usage
console.log(calculator.add(5, 3)); // Output: 8
console.log(calculator.subtract(10, 4)); // Output: 6
console.log(calculator.multiply(3, 7)); // Output: 21
console.log(calculator.divide(15, 3)); // Output: 5
console.log(calculator.divide(10, 0)); // Output: "Cannot divide by zero"
```

### Exercise 5.2
Create a `student` object with properties for `name`, `grades` (an array), and methods for `addGrade`, `getAverage`, and `getHighest`. Implement the methods to perform their respective operations.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
const student = {
  name: "Emma",
  grades: [85, 92, 78, 90],
  
  addGrade: function(grade) {
    if (grade >= 0 && grade <= 100) {
      this.grades.push(grade);
      return true;
    }
    return false;
  },
  
  getAverage: function() {
    if (this.grades.length === 0) return 0;
    
    const sum = this.grades.reduce((total, grade) => total + grade, 0);
    return sum / this.grades.length;
  },
  
  getHighest: function() {
    if (this.grades.length === 0) return null;
    
    return Math.max(...this.grades);
  }
};

// Example usage
console.log(student.name); // Output: "Emma"
console.log(student.grades); // Output: [85, 92, 78, 90]
console.log(student.addGrade(95)); // Output: true
console.log(student.grades); // Output: [85, 92, 78, 90, 95]
console.log(student.getAverage()); // Output: 88
console.log(student.getHighest()); // Output: 95
```

## 6. Functions are Also Objects

### Exercise 6.1
Create a function `counter` that has properties `count` (initialized to 0) and methods `increment` and `reset`. The function itself should return the current count when called.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function counter() {
  return counter.count;
}

counter.count = 0;

counter.increment = function() {
  counter.count++;
  return counter.count;
};

counter.reset = function() {
  counter.count = 0;
  return counter.count;
};

// Example usage
console.log(counter()); // Output: 0
console.log(counter.increment()); // Output: 1
console.log(counter.increment()); // Output: 2
console.log(counter()); // Output: 2
console.log(counter.reset()); // Output: 0
console.log(counter()); // Output: 0
```

### Exercise 6.2
Create a function `createMultiplier` that takes a factor parameter and returns a new function that multiplies its input by that factor. Add a property to the returned function that displays the factor used.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function createMultiplier(factor) {
  const multiplier = function(number) {
    return number * factor;
  };
  
  multiplier.factor = factor;
  
  return multiplier;
}

// Example usage
const double = createMultiplier(2);
const triple = createMultiplier(3);

console.log(double(5)); // Output: 10
console.log(triple(5)); // Output: 15
console.log(double.factor); // Output: 2
console.log(triple.factor); // Output: 3
```

## 7. `this` in Functions

### Exercise 7.1
Create an object `user` with properties `firstName` and `lastName`, and a method `getFullName` that returns the full name. Then create another object `admin` that borrows the `getFullName` method from `user`.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
const user = {
  firstName: "John",
  lastName: "Doe",
  getFullName: function() {
    return `${this.firstName} ${this.lastName}`;
  }
};

const admin = {
  firstName: "Admin",
  lastName: "User"
};

// Example usage
console.log(user.getFullName()); // Output: "John Doe"

// Borrowing the method
console.log(user.getFullName.call(admin)); // Output: "Admin User"

// Alternative way to borrow
admin.getFullName = user.getFullName;
console.log(admin.getFullName()); // Output: "Admin User"
```

### Exercise 7.2
Create a constructor function `Person` with properties `name` and `age` and a method `introduce` that outputs an introduction. Then create multiple instances and demonstrate how `this` refers to each instance.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
  
  this.introduce = function() {
    return `Hi, I'm ${this.name} and I'm ${this.age} years old.`;
  };
}

// Example usage
const person1 = new Person("Alice", 28);
const person2 = new Person("Bob", 32);

console.log(person1.introduce()); // Output: "Hi, I'm Alice and I'm 28 years old."
console.log(person2.introduce()); // Output: "Hi, I'm Bob and I'm 32 years old."

// Demonstrating how 'this' is bound to the global object when not called as a method
const introduceFn = person1.introduce;
// This will result in undefined values for this.name and this.age
// console.log(introduceFn()); // Output: "Hi, I'm undefined and I'm undefined years old."

// Fix with bind
const boundIntroduce = person1.introduce.bind(person1);
console.log(boundIntroduce()); // Output: "Hi, I'm Alice and I'm 28 years old."
```

## 8. Rest Parameters and Variable-Length Argument Lists

### Exercise 8.1
Create a function `sum` that takes any number of arguments and returns their sum.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

// Example usage
console.log(sum(1, 2)); // Output: 3
console.log(sum(1, 2, 3, 4, 5)); // Output: 15
console.log(sum()); // Output: 0
```

### Exercise 8.2
Create a function `logWithTimestamp` that takes a timestamp as its first parameter and logs it along with any number of additional arguments.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function logWithTimestamp(timestamp, ...messages) {
  const formattedTimestamp = new Date(timestamp).toISOString();
  
  console.log(`[${formattedTimestamp}]`, ...messages);
}

// Example usage
const now = Date.now();
logWithTimestamp(now, "User logged in"); // Output: "[2023-06-15T14:30:45.123Z] User logged in"
logWithTimestamp(now, "Error", "Database connection failed", { code: 500 }); 
// Output: "[2023-06-15T14:30:45.123Z] Error Database connection failed { code: 500 }"
```

## 9. Destructuring Assignment

### Exercise 9.1
Use destructuring to extract values from an array representing RGB color values.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
// Original array
const rgb = [255, 140, 0]; // RGB for dark orange

// Destructuring assignment
const [red, green, blue] = rgb;

// Example usage
console.log(`R: ${red}, G: ${green}, B: ${blue}`); // Output: "R: 255, G: 140, B: 0"

// With default values for missing elements
const partialColor = [255, 140];
const [r, g, b = 0] = partialColor;
console.log(`R: ${r}, G: ${g}, B: ${b}`); // Output: "R: 255, G: 140, B: 0"
```

### Exercise 9.2
Use destructuring to extract specific properties from a user object.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
// Original object
const user = {
  id: 42,
  displayName: "jdoe",
  fullName: {
    firstName: "John",
    lastName: "Doe"
  },
  role: "admin",
  settings: {
    theme: "dark",
    notifications: true
  }
};

// Basic destructuring
const { id, displayName, role } = user;
console.log(id, displayName, role); // Output: 42 "jdoe" "admin"

// Nested destructuring
const { fullName: { firstName, lastName }, settings: { theme } } = user;
console.log(firstName, lastName, theme); // Output: "John" "Doe" "dark"

// Renaming variables
const { displayName: username, role: userRole } = user;
console.log(username, userRole); // Output: "jdoe" "admin"

// Default values
const { age = 30 } = user;
console.log(age); // Output: 30 (default value since age doesn't exist in user)
```

## 10. Destructuring Function Arguments in Parameters

### Exercise 10.1
Create a function `printUserInfo` that takes an object as a parameter and uses destructuring in the parameter list to extract `name`, `age`, and an optional `email` property with a default value.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function printUserInfo({ name, age, email = "Not provided" }) {
  console.log(`Name: ${name}, Age: ${age}, Email: ${email}`);
}

// Example usage
const user1 = { name: "Alice", age: 28, email: "alice@example.com" };
const user2 = { name: "Bob", age: 32 };

printUserInfo(user1); // Output: "Name: Alice, Age: 28, Email: alice@example.com"
printUserInfo(user2); // Output: "Name: Bob, Age: 32, Email: Not provided"
```

### Exercise 10.2
Create a function `calculateCartTotal` that uses destructuring in the parameter list to extract `items` (an array) and an optional `discount` (with a default value of 0) from a shopping cart object. The function should calculate the total price of all items and apply the discount.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function calculateCartTotal({ items, discount = 0, tax = 0 }) {
  const subtotal = items.reduce((total, item) => total + (item.price * item.quantity), 0);
  const discountAmount = subtotal * (discount / 100);
  const taxAmount = (subtotal - discountAmount) * (tax / 100);
  
  return {
    subtotal,
    discount: discountAmount,
    tax: taxAmount,
    total: subtotal - discountAmount + taxAmount
  };
}

// Example usage
const cart1 = {
  items: [
    { name: "T-shirt", price: 20, quantity: 2 },
    { name: "Jeans", price: 50, quantity: 1 }
  ],
  discount: 10,
  tax: 8
};

const cart2 = {
  items: [
    { name: "Shoes", price: 80, quantity: 1 }
  ]
};

console.log(calculateCartTotal(cart1));
// Output: { subtotal: 90, discount: 9, tax: 6.48, total: 87.48 }

console.log(calculateCartTotal(cart2));
// Output: { subtotal: 80, discount: 0, tax: 0, total: 80 }
```

## 11. Bonus: Arrow Functions

### Exercise 11.1
Convert the following function declarations to arrow functions:

```javascript
function double(x) {
  return x * 2;
}

function greet(name) {
  return `Hello, ${name}!`;
}

function isEven(num) {
  return num % 2 === 0;
}
```

**Expected Answer:**
```javascript
const double = x => x * 2;

const greet = name => `Hello, ${name}!`;

const isEven = num => num % 2 === 0;

// Example usage
console.log(double(5)); // Output: 10
console.log(greet("Alice")); // Output: "Hello, Alice!"
console.log(isEven(4)); // Output: true
```

### Exercise 11.2
Explain how arrow functions treat `this` differently from regular functions by creating an example with a button click.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
// Object with regular and arrow function methods
const counter = {
  count: 0,
  
  // Regular function - 'this' refers to the counter object
  incrementRegular: function() {
    this.count++;
    console.log("Regular function count:", this.count);
  },
  
  // Arrow function - 'this' is lexically bound (refers to the surrounding scope)
  incrementArrow: () => {
    this.count++; // 'this' does not refer to counter object!
    console.log("Arrow function count:", this.count);
  },
  
  // Method that demonstrates the difference
  setupClickHandlers: function() {
    // Assume we have a button with id "regularBtn"
    const regularBtn = document.getElementById("regularBtn");
    if (regularBtn) {
      // Regular function loses 'this' context when used as callback
      regularBtn.addEventListener("click", function() {
        this.incrementRegular(); // Error: this.incrementRegular is not a function
      });
    }
    
    // Assume we have a button with id "arrowBtn"
    const arrowBtn = document.getElementById("arrowBtn");
    if (arrowBtn) {
      // Arrow function maintains lexical 'this' context
      arrowBtn.addEventListener("click", () => {
        this.incrementRegular(); // Works correctly, 'this' refers to counter
      });
    }
    
    // Alternative fix for regular function using bind
    const boundBtn = document.getElementById("boundBtn");
    if (boundBtn) {
      boundBtn.addEventListener("click", function() {
        this.incrementRegular();
      }.bind(this)); // Explicitly bind 'this'
    }
  }
};

/* 
Explanation:
- Arrow functions do not have their own 'this' context. They inherit 'this' from the surrounding scope.
- Regular functions have their own 'this' context, which depends on how they are called.
- When using regular functions as callbacks, 'this' often refers to the element that triggered the event.
- When using arrow functions as callbacks, 'this' maintains its lexical binding from where it was defined.
- This makes arrow functions particularly useful for callbacks where you want to preserve 'this' context.
*/
```
