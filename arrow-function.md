# JavaScript Arrow Functions - Hands-on Exercises

Related reading: 
- https://javascript.info/arrow-functions-basics
- https://javascript.info/object-methods
- https://javascript.info/arrow-functions
- https://javascript.info/bind

## Exercise 1: Convert to Arrow Functions
Convert the following traditional function expressions into arrow functions.

```js
// a) Convert this function to an arrow function
function add(a, b) {
    return a + b;
}

// b) Convert this function to an arrow function
const square = function (x) {
    return x * x;
};

// c) Convert this function to an arrow function
const greet = function(name) {
    return "Hello, " + name + "!";
};
```

✅ **Expected Output:**  
If you call the functions with `console.log(add(3, 4))`, `console.log(square(5))`, and `console.log(greet("Alice"))`, they should still work the same way.

---

## Exercise 2: Implicit Return
Rewrite the functions below using arrow functions **with implicit return** (i.e., no `{}` or `return` keyword).

```js
// a) Convert this function to an arrow function with implicit return
const multiplyByTwo = function (num) {
    return num * 2;
};

// b) Convert this function to an arrow function with implicit return
const getFullName = function (firstName, lastName) {
    return firstName + " " + lastName;
};
```

✅ **Expected Output:**  
```js
console.log(multiplyByTwo(10)); // 20
console.log(getFullName("John", "Doe")); // "John Doe"
```

---



## Exercise 3: Using Arrow Functions in `map()`
Use arrow functions to simplify the following code.

```js
const numbers = [1, 2, 3, 4, 5];

// a) Double each number in the array
const doubled = numbers.map(function (num) {
    return num * 2;
});

// b) Convert an array of words to uppercase
const words = ["hello", "world"];
const uppercased = words.map(function (word) {
    return word.toUpperCase();
});
```

✅ **Expected Output:**  
```js
console.log(doubled); // [2, 4, 6, 8, 10]
console.log(uppercased); // ["HELLO", "WORLD"]
```

---

## Exercise 4: Filtering an Array
Use arrow functions with `filter()` to get all even numbers from the array.

```js
const numbers = [10, 15, 20, 25, 30];

// Get only even numbers using filter()
const evenNumbers = numbers.filter(function (num) {
    return num % 2 === 0;
});

console.log(evenNumbers);
```

✅ **Expected Output:**  
```js
[10, 20, 30]
```

---

## Exercise 5: Reducing an Array
Use an arrow function with `reduce()` to find the sum of all numbers in the array.

```js
const numbers = [1, 2, 3, 4, 5];

// Sum all numbers using reduce()
const sum = numbers.reduce(function (acc, num) {
    return acc + num;
}, 0);

console.log(sum);
```

✅ **Expected Output:**  
```js
15
```

---

## Exercise 6: Arrow Function and `this`
What will the following code output in Browser console? Explain why.

```js
const person = {
    name: "Alice",
    greet: function() {
        setTimeout(() => {
            console.log("Hello, my name is " + this.name);
        }, 1000);
    }
};

person.greet();
```

✅ **Expected Output:**  
It should print `"Hello, my name is Alice"` after 1 second.  We should understand that arrow functions **do not have their own `this`** and inherit `this` from their surrounding scope.

Now Change the arrow function to a regular function expression. What will the following code output in **Browser console**? Explain why.

```js
const person = {
    name: "Alice",
    greet: function() {
        setTimeout(function() {
            console.log("Hello, my name is " + this.name);
        }, 1000);
    }
};

person.greet();
```

✅ **Expected Output:**  
It should print `"Hello, my name is undefined"` after 1 second.  Explain why?

---

## Exercise 7: Understanding `this` in Regular Functions
What does the `this` keyword refer to inside a regular function in JavaScript?

- A) The global object
- B) The function itself
- C) The object that called the function
- D) `undefined` inside strict mode

**Answer:**
C) The object that called the function.

---

## Exercise 8: `this` in Arrow Functions

What is the main difference between how `this` behaves in regular functions and arrow functions in JavaScript?

- A) Arrow functions don't have a `this` keyword.
- B) Arrow functions inherit `this` from their surrounding context (lexical scoping).
- C) Regular functions always bind `this` to the global object.
- D) `this` behaves the same in both regular functions and arrow functions.

**Answer:**
B) Arrow functions inherit `this` from their surrounding context (lexical scoping).

---

## Exercise 9: Difference between `this` in Regular functions and Arrow Function
```javascript
const obj = {
    value: 42,
    regularFunction: function() {
        console.log(this.value);  // What will be logged here?
    },
    arrowFunction: () => {
        console.log(this.value);  // What will be logged here?
    }
};

obj.regularFunction();  // Call regular function
obj.arrowFunction();    // Call arrow function
```

Question: What will be logged when calling `obj.regularFunction()` and `obj.arrowFunction()`? Explain why.

✅ **Expected Output:**  

- `obj.regularFunction()` will log `42`, because the `this` in regular functions refers to the object that called it (obj).
- `obj.arrowFunction()` will log `undefined`, because the `this` in arrow functions is lexically bound to the surrounding context, which is likely the global object (or `undefined` in strict mode).

---

## Exercise 10: Using `this` with Arrow Functions and `.bind()`
```js
const person = {
    name: 'John',
    greet: function() {
        console.log(`Hello, my name is ${this.name}`);
    }
};

const greetPerson = person.greet;
greetPerson();  // What will be logged here?

const boundGreet = person.greet.bind(person);
boundGreet();   // What will be logged here?
```
Question: What will be logged in each case? Explain the behavior of this and how .bind() changes it.


✅ **Expected Output:**  

`greetPerson()` will log `Hello`, my name is `undefined`, because the function is called outside of the person object, so `this` refers to the global object or `undefined`.
`boundGreet()` will log `Hello`, my name is `John`, because `.bind(person)` explicitly binds `this` to the `person object`.

---

## Exercise 11: `this` with .bind() vs Arrow Functions

Compare binding `this` explicitly with `.bind` versus using arrow functions.

```js

const user = {
  name: 'David',
  
  greetRegular: function() {
    return `Hello, I'm ${this.name}`;
  },
  
  greetArrow: () => {
    return `Hi, I'm ${this.name}`;
  },
  
  getFunctions: function() {
    return {
      // Using .bind()
      boundFunction: this.greetRegular.bind(this),
      
      // Using arrow function
      arrowFunction: () => this.greetRegular()
    };
  }
};

const functions = user.getFunctions();
console.log(functions.boundFunction());
console.log(functions.arrowFunction());

```
Question: Understand the code and be able to explain how `.bind()` changed the behaviour. 

--- 

## Exercise 12: Understanding the necessity of `that` variable

```js
const person = {
  name: "Alice",
  regularMethod() {
    const that = this;
    setTimeout(function() {
      console.log("Using that:", that.name);
      console.log("Using this:", this.name);
    }, 100);
  }
};

person.regularMethod();
```

Question: 

- Explain what happens in the following code and why the `that` variable is necessary. 
- If we don't use `that` variable here, can we use `.bind()` to lead to the same result?

## Exercise 13: Difference Between `.call()` and `.bind()` in JavaScript

The `.call()` and `.bind()` methods in JavaScript both allow you to control what `this` refers to, but they work differently:

### `.call()`

`.call()` invokes the function immediately with a specified `this` value and arguments:

```javascript
function greet(greeting) {
  return `${greeting}, ${this.name}`;
}

const person = { name: 'Alice' };

// Immediately calls greet() with person as 'this'
const result = greet.call(person, 'Hello');
console.log(result); // "Hello, Alice"
```

Key characteristics:
- Executes the function right away
- First argument sets the `this` value
- Additional arguments are passed to the function directly
- Returns whatever the function returns

### `.bind()`

`.bind()` creates a new function with a bound `this` value without executing it:

```javascript
function greet(greeting) {
  return `${greeting}, ${this.name}`;
}

const person = { name: 'Alice' };

// Creates a new function with 'person' bound as 'this'
const boundGreet = greet.bind(person);

// Later execution
const result = boundGreet('Hello');
console.log(result); // "Hello, Alice"

// You can also pre-bind arguments
const sayHello = greet.bind(person, 'Hello');
console.log(sayHello()); // "Hello, Alice"
```

Key characteristics:
- Returns a new function without executing it
- The new function has `this` permanently bound
- Can pre-bind arguments as well
- The bound function can be called later or passed as a callback

### Main Differences

1. **Execution timing**:
   - `.call()` executes immediately
   - `.bind()` returns a function for later execution

2. **Use cases**:
   - `.call()` is useful for one-time function calls with a specific context
   - `.bind()` is ideal for event handlers, callbacks, and when you need to reuse a function with a fixed context

3. **Permanence**:
   - `.call()` temporarily sets `this` for a single invocation
   - `.bind()` permanently sets `this` for all future invocations of the bound function

4. **Return value**:
   - `.call()` returns the function's result
   - `.bind()` returns a new function
