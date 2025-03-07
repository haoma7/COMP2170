# JavaScript Constructorand Class Exercises

## 1. Constructor Functions and `new`

### Exercise 1.1
Create a constructor function called `Person` that takes `name` and `age` parameters. Initialize these properties in the constructor. Then create two different people using the `new` keyword.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

const person1 = new Person('Alice', 25);
const person2 = new Person('Bob', 30);

console.log(person1); // Person { name: 'Alice', age: 25 }
console.log(person2); // Person { name: 'Bob', age: 30 }
```

### Exercise 1.2
What happens if you call a constructor function without the `new` keyword? Modify the `Person` constructor to handle this case correctly.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function Person(name, age) {
  // Guard against calling without new
  if (!(this instanceof Person)) {
    return new Person(name, age);
  }
  
  this.name = name;
  this.age = age;
}

const person1 = Person('Charlie', 35); // Called without new
console.log(person1); // Person { name: 'Charlie', age: 35 }
```

### Exercise 1.3
Create a constructor function `Book` with properties for `title`, `author`, and `year`. Add a method to calculate how old the book is. Create a book object and call the method.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function Book(title, author, year) {
  this.title = title;
  this.author = author;
  this.year = year;
  
  this.getAge = function() {
    return new Date().getFullYear() - this.year;
  };
}

const myBook = new Book('JavaScript: The Good Parts', 'Douglas Crockford', 2008);
console.log(`${myBook.title} is ${myBook.getAge()} years old`);
// JavaScript: The Good Parts is 17 years old (as of 2025)
```

## 2. Methods in Constructor

### Exercise 2.1
Improve the `Book` constructor by moving the `getAge` method to the prototype instead of creating it for each instance. Create two book instances and verify they share the same method.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function Book(title, author, year) {
  this.title = title;
  this.author = author;
  this.year = year;
}

Book.prototype.getAge = function() {
  return new Date().getFullYear() - this.year;
};

const book1 = new Book('JavaScript: The Good Parts', 'Douglas Crockford', 2008);
const book2 = new Book('Eloquent JavaScript', 'Marijn Haverbeke', 2011);

console.log(`${book1.title} is ${book1.getAge()} years old`);
console.log(`${book2.title} is ${book2.getAge()} years old`);
console.log(book1.getAge === book2.getAge); // true - same method reference
```

### Exercise 2.2
Create a constructor function `Calculator` with methods for `add`, `subtract`, `multiply`, and `divide`. Place these methods on the prototype. Then create an instance and perform each operation.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function Calculator() {
  this.result = 0;
}

Calculator.prototype.add = function(num) {
  this.result += num;
  return this;
};

Calculator.prototype.subtract = function(num) {
  this.result -= num;
  return this;
};

Calculator.prototype.multiply = function(num) {
  this.result *= num;
  return this;
};

Calculator.prototype.divide = function(num) {
  if (num === 0) {
    throw new Error("Cannot divide by zero");
  }
  this.result /= num;
  return this;
};

Calculator.prototype.getResult = function() {
  return this.result;
};

const calc = new Calculator();
calc.add(10).subtract(2).multiply(3).divide(2);
console.log(calc.getResult()); // 12
```

### Exercise 2.3
Create a `BankAccount` constructor with properties for `owner` and `balance`. Add methods for `deposit`, `withdraw`, and `checkBalance`. Ensure that the balance cannot go below 0.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
function BankAccount(owner, initialBalance = 0) {
  this.owner = owner;
  this.balance = initialBalance;
}

BankAccount.prototype.deposit = function(amount) {
  if (amount <= 0) {
    console.log("Deposit amount must be positive");
    return false;
  }
  
  this.balance += amount;
  console.log(`Deposited $${amount}. New balance: $${this.balance}`);
  return true;
};

BankAccount.prototype.withdraw = function(amount) {
  if (amount <= 0) {
    console.log("Withdrawal amount must be positive");
    return false;
  }
  
  if (amount > this.balance) {
    console.log("Insufficient funds");
    return false;
  }
  
  this.balance -= amount;
  console.log(`Withdrew $${amount}. New balance: $${this.balance}`);
  return true;
};

BankAccount.prototype.checkBalance = function() {
  console.log(`Balance for ${this.owner}: $${this.balance}`);
  return this.balance;
};

const account = new BankAccount("Alice", 1000);
account.checkBalance();  // Balance for Alice: $1000
account.deposit(500);    // Deposited $500. New balance: $1500
account.withdraw(200);   // Withdrew $200. New balance: $1300
account.withdraw(2000);  // Insufficient funds
```

## 3. Class Syntax

### Exercise 3.1
Rewrite the `Person` constructor function using ES6 class syntax. Include a method `greet()` that returns a greeting string.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  
  greet() {
    return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
  }
}

const person = new Person('Alice', 25);
console.log(person.greet()); // Hello, my name is Alice and I am 25 years old.
```

### Exercise 3.2
Create a `Student` class that extends the `Person` class. Add a property for `grade` and a method `study()` that returns a string. Override the `greet()` method to include the student's grade.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  
  greet() {
    return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
  }
}

class Student extends Person {
  constructor(name, age, grade) {
    super(name, age);
    this.grade = grade;
  }
  
  study() {
    return `${this.name} is studying hard to maintain grade ${this.grade}.`;
  }
  
  greet() {
    return `${super.greet()} I am in grade ${this.grade}.`;
  }
}

const student = new Student('Bob', 18, 'A');
console.log(student.greet()); // Hello, my name is Bob and I am 18 years old. I am in grade A.
console.log(student.study()); // Bob is studying hard to maintain grade A.
```

### Exercise 3.3
Create a `Shape` class with a method `calculateArea()`. Then create two subclasses: `Circle` (with radius property) and `Rectangle` (with width and height properties). Override the `calculateArea()` method in both subclasses.

```javascript
// Your code here
```

**Expected Answer:**
```javascript
class Shape {
  constructor() {
    if (this.constructor === Shape) {
      throw new Error("Cannot instantiate abstract class");
    }
  }
  
  calculateArea() {
    throw new Error("Method 'calculateArea()' must be implemented by subclasses");
  }
}

class Circle extends Shape {
  constructor(radius) {
    super();
    this.radius = radius;
  }
  
  calculateArea() {
    return Math.PI * this.radius * this.radius;
  }
}

class Rectangle extends Shape {
  constructor(width, height) {
    super();
    this.width = width;
    this.height = height;
  }
  
  calculateArea() {
    return this.width * this.height;
  }
}

const circle = new Circle(5);
console.log(`Circle area: ${circle.calculateArea().toFixed(2)}`); // Circle area: 78.54

const rectangle = new Rectangle(4, 6);
console.log(`Rectangle area: ${rectangle.calculateArea()}`); // Rectangle area: 24
```

