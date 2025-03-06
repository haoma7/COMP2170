# JavaScript Exercises: Closures

## Exercise 1: Basic Closure

### Objective
Understand how a function retains access to variables in its lexical scope even after execution.

### Instructions
1. Write a function `createCounter` that returns another function.
2. The returned function should increment a counter and return the updated value each time it is called.

```javascript
function createCounter() {
    let count = 0;
    return function() {
        count++;
        return count;
    };
}

const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3
```

### Task
- Explain why the `count` variable is not reset to 0 each time `counter` is called.

---

## Exercise 2: Private Variables with Closures

### Objective
Learn how closures can be used to create private variables.

### Instructions
1. Create a function `secretMessage` that takes a string and returns a function.
2. The returned function, when called, should return the stored secret message.

```javascript
function secretMessage(secret) {
    return function() {
        return secret;
    };
}

const mySecret = secretMessage("JavaScript is awesome!");
console.log(mySecret()); // "JavaScript is awesome!"
```


---

## Exercise 3: Function Factory

### Objective
Understand how closures can be used to generate functions dynamically.

### Instructions
1. Create a function `multiplyBy` that takes a number `x` and returns a function.
2. The returned function should take another number `y` and return `x * y`.

```javascript
function multiplyBy(x) {
    return function(y) {
        return x * y;
    };
}

const double = multiplyBy(2);
const triple = multiplyBy(3);

console.log(double(5)); // 10
console.log(triple(4)); // 12
```

### Task
- Create a `quadruple` function using `multiplyBy` and test it.

---

## Exercise 4: Timer with Closures

### Objective
Use closures to manage state over time.

### Instructions
1. Write a function `countdown` that takes a number `n` and returns a function.
2. The returned function, when called, should decrease `n` by 1 and return the updated value.
3. When `n` reaches 0, it should return "Time's up!" instead.

```javascript
function countdown(n) {
    return function() {
        if (n > 0) {
            return n--;
        } else {
            return "Time's up!";
        }
    };
}

const timer = countdown(3);
console.log(timer()); // 3
console.log(timer()); // 2
console.log(timer()); // 1
console.log(timer()); // "Time's up!"
```

### Task
- Modify it to take a callback function that runs when the countdown reaches 0.

---

## Exercise 5: Managing Subscriptions with Closures

### Objective
Use closures to store and manage multiple values dynamically.

### Instructions
1. Create a function `createSubscriptionManager` that allows adding and notifying subscribers.
2. It should return an object with `subscribe` and `notify` methods.

```javascript
function createSubscriptionManager() {
    let subscribers = [];
    
    return {
        subscribe: function(callback) {
            subscribers.push(callback);
        },
        notify: function(data) {
            subscribers.forEach(callback => callback(data));
        }
    };
}

const manager = createSubscriptionManager();
manager.subscribe(data => console.log("Subscriber 1 received:", data));
manager.subscribe(data => console.log("Subscriber 2 received:", data));
manager.notify("Hello, subscribers!");
```

### Task
- Modify it to allow unsubscribing from notifications.


