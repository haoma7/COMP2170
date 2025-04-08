# 🧪 Asynchronous JavaScript: Beginner Practice Exercises

## 1. Understanding Callbacks
**Question:**  
What is a callback function in JavaScript? Write a simple example of using a callback function.
<details>
<summary>💡 Click to reveal answer</summary>
  
```js
// A callback function is a function passed to another function as an argument,
// which is then invoked inside the outer function to complete an action.

function greet(name, callback) {
  console.log("Hello " + name);
  callback();
}

// Using the function with a callback
greet("John", function() {
  console.log("The greeting has been displayed");
});

// Output:
// Hello John
// The greeting has been displayed
```
</details>

---

## 2. Callback for Asynchronous Operations
**Question:**  
Write a function that simulates fetching user data after a 2-second delay using a callback function.

<details>
<summary>💡 Click to reveal answer</summary>
 
```js
function fetchUserData(userId, callback) {
  console.log("Fetching user data...");
  
  // Simulate network delay with setTimeout
  setTimeout(function() {
    // Simulate a successful response with user data
    const userData = {
      id: userId,
      name: "John Doe",
      email: "john@example.com"
    };
    
    callback(null, userData); // First parameter is for errors (null means no error)
  }, 2000);
}

// Using the function
fetchUserData(123, function(error, user) {
  if (error) {
    console.error("Error fetching user:", error);
  } else {
    console.log("User data received:", user);
  }
});

// Output (after 2 seconds):
// Fetching user data...
// User data received: {id: 123, name: "John Doe", email: "john@example.com"}
```

</details>

---

## 3. Callback Hell Example
**Question:**  
Below is an example of "callback hell" (deeply nested callbacks). What problems do you see with this code structure?

```js
getUserData(userId, function(userData) {
  getPostsByUser(userData.id, function(posts) {
    getCommentsForPost(posts[0].id, function(comments) {
      displayUserActivity(userData, posts, comments, function() {
        console.log("User activity displayed");
      });
    });
  });
});
```
<details>
<summary>💡 Click to reveal answer</summary>
 
```
Problems with the callback hell code:

1. Poor readability: The deeply nested structure makes it hard to follow the code execution flow.
2. Error handling is difficult: Each callback would need its own error handling.
3. Code maintenance: Adding more functionality or fixing bugs becomes complex.
4. Debugging challenges: Stack traces are harder to understand with nested callbacks.
5. Sequential dependency: Each operation must wait for the previous one to complete.
6. The code expands horizontally, which makes it harder to fit within standard code style guidelines.
```
</details>

---

## 4. Creating a Simple Promise
**Question:**  
Create a simple Promise that resolves with a "Hello, world!" message after 1 second.
<details>
<summary>💡 Click to reveal answer</summary>
 
```js
const greeting = new Promise(function(resolve, reject) {
  setTimeout(function() {
    resolve("Hello, world!");
  }, 1000);
});

// Using the promise
greeting
  .then(function(message) {
    console.log(message);  // Outputs: Hello, world!
  });
```

</details>

---

## 5. Promise with Success and Error
**Question:**  
Create a Promise that simulates a coin flip. If the random result is heads (true), resolve the promise with "Heads!". If it's tails (false), reject the promise with "Tails!".

<details> <summary>💡 Click to reveal answer</summary>  
```js
const coinFlip = new Promise(function(resolve, reject) {
  // Generate random boolean (true or false)
  const isHeads = Math.random() > 0.5;
  
  if (isHeads) {
    resolve("Heads!");
  } else {
    reject("Tails!");
  }
});

// Using the promise with both success and error handling
coinFlip
  .then(function(result) {
    console.log("Success:", result);  // If heads
  })
  .catch(function(error) {
    console.log("Error:", error);     // If tails
  });
```

</details>

---

## 6. Converting Callback to Promise
**Question:**  
Convert this callback-based function to a Promise-based function:

```js
function getRandomNumber(max, callback) {
  setTimeout(function() {
    const randomNum = Math.floor(Math.random() * max);
    callback(randomNum);
  }, 1000);
}
```

💡 Click to reveal answer
```js
function getRandomNumber(max) {
  return new Promise(function(resolve, reject) {
    setTimeout(function() {
      const randomNum = Math.floor(Math.random() * max);
      resolve(randomNum);
    }, 1000);
  });
}

// Using the Promise-based function
getRandomNumber(10)
  .then(function(num) {
    console.log("Random number:", num);
  });
```

</details>

---

## 7. Understanding Promise States
**Question:**  
What are the three possible states of a Promise? Briefly explain each.

<details> <summary>💡 Click to reveal answer</summary>  
```
The three states of a Promise:

1. Pending: Initial state, neither fulfilled nor rejected. The Promise is still in progress.

2. Fulfilled: The operation completed successfully, and the Promise has a resulting value (accessed via .then()).

3. Rejected: The operation failed, and the Promise has a reason for the failure (accessed via .catch()).

Once a Promise is either fulfilled or rejected, it is considered "settled" and can't change to another state.
```

</details>

---

## 8. Using then() with Promises
**Question:**  
Write code using a Promise to fetch a user and then log their name to the console.

<details> <summary>💡 Click to reveal answer</summary>  
```js
function fetchUser() {
  return new Promise(function(resolve, reject) {
    setTimeout(function() {
      const user = { id: 1, name: "Alice" };
      resolve(user);
    }, 1000);
  });
}

fetchUser()
  .then(function(user) {
    console.log("User name:", user.name);  // Outputs: User name: Alice
  });
```

</details>

---

## 9. Chain Multiple Promises
**Question:**  
Using Promise chaining, first fetch a user, then fetch their posts, and finally log the user's name and the number of posts.

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
function fetchUser() {
  return new Promise(function(resolve) {
    setTimeout(function() {
      resolve({ id: 1, name: "Alice" });
    }, 1000);
  });
}

function fetchPosts(userId) {
  return new Promise(function(resolve) {
    setTimeout(function() {
      resolve(["Post 1", "Post 2", "Post 3"]);
    }, 1000);
  });
}

// Chaining promises
fetchUser()
  .then(function(user) {
    console.log("User:", user.name); 
    return fetchPosts(user.id);  // Return a new promise
  })
  .then(function(posts) {
    console.log("Number of posts:", posts.length);
  });

// Output (after 2 seconds):
// User: Alice
// Number of posts: 3
```

</details>

---

## 10. Error Handling with catch()
**Question:**  
What does the `.catch()` method do in a Promise chain? Modify the code below to handle potential errors:

```js
fetchData()
  .then(function(data) {
    processData(data);
  });
```

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// The .catch() method handles any rejected promises in the chain,
// similar to a try/catch block in synchronous code.

fetchData()
  .then(function(data) {
    processData(data);
  })
  .catch(function(error) {
    console.error("An error occurred:", error);
  });

// You can also handle errors in individual .then() callbacks:
fetchData()
  .then(function(data) {
    try {
      processData(data);
    } catch (error) {
      console.error("Error processing data:", error);
    }
  })
  .catch(function(error) {
    console.error("Error fetching data:", error);
  });
```

</details>

---

## 11. Using finally() with Promises
**Question:**  
What does the `.finally()` method do in a Promise chain? Add it to the code below:

```js
fetchData()
  .then(function(data) {
    displayData(data);
  })
  .catch(function(error) {
    showError(error);
  });
```

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// The .finally() method executes code regardless of whether the promise
// was fulfilled or rejected. It's useful for cleanup operations.

fetchData()
  .then(function(data) {
    displayData(data);
  })
  .catch(function(error) {
    showError(error);
  })
  .finally(function() {
    hideLoadingSpinner();  // This runs whether the promise succeeded or failed
    console.log("Operation complete");
  });
```

</details>

---

## 12. Promise vs Callback - Advantages
**Question:**  
List at least three advantages of using Promises over traditional callbacks.

<details> <summary>💡 Click to reveal answer</summary>  
  
```
Advantages of Promises over callbacks:

1. Better Error Handling: Promises have built-in error handling through .catch(), making it easier to handle and propagate errors.

2. Chaining: Promises can be easily chained using .then(), avoiding deep nesting ("callback hell").

3. Control Flow: Promises make asynchronous code look more like synchronous code, improving readability.

4. Guaranteed Call: A callback might be called multiple times, but a Promise is resolved or rejected exactly once.

5. Predictable: Promises always execute in the same order they were created, making behavior more predictable.

6. Better Debugging: Promise chains provide better stack traces for debugging.
```
</details>

---

## 13. Introduction to async/await
**Question:**  
What is the purpose of the `async` and `await` keywords in JavaScript? How do they relate to Promises?

<details> <summary>💡 Click to reveal answer</summary>  
  
```
async/await purpose and relation to Promises:

- `async`: This keyword is used before a function declaration to mark it as asynchronous. An async function always returns a Promise automatically.

- `await`: This keyword can only be used inside an async function. It pauses the execution of the function until the Promise is resolved or rejected, and then returns the resolved value.

- Relation to Promises: async/await is built on top of Promises - it's syntactic sugar that makes working with Promises more like writing synchronous code, improving readability and maintainability.

- Under the hood, async/await uses Promises, but provides a cleaner syntax for writing asynchronous code.
```

</details>

---

## 14. Basic async/await Example
**Question:**  
Convert this Promise-based code to use async/await:

```js
function fetchUser() {
  return new Promise(function(resolve) {
    setTimeout(function() {
      resolve({ name: "Alice" });
    }, 1000);
  });
}

function displayUser() {
  fetchUser()
    .then(function(user) {
      console.log(user.name);
    });
}

displayUser();
```

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
function fetchUser() {
  return new Promise(function(resolve) {
    setTimeout(function() {
      resolve({ name: "Alice" });
    }, 1000);
  });
}

// Using async/await
async function displayUser() {
  const user = await fetchUser();  // Wait for the Promise to resolve
  console.log(user.name);          // This line runs after the Promise resolves
}

displayUser();
```

</details>

---

## 15. Error Handling with async/await
**Question:**  
How do you handle errors when using async/await? Add error handling to the function below:

```js
async function fetchData() {
  const response = await fetch('https://api.example.com/data');
  const data = await response.json();
  return data;
}
```

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// With async/await, we can use regular try/catch blocks for error handling

async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    const data = await response.json();
    return data;
  } catch (error) {
    console.error("Error fetching data:", error);
    throw error;  // Re-throw to allow calling code to handle it
  }
}

// Usage:
async function displayData() {
  try {
    const data = await fetchData();
    console.log("Data received:", data);
  } catch (error) {
    console.error("Could not display data:", error);
  }
}
```

</details>

---

## 16. Callback Hell vs. Promises vs. async/await
**Question:**  
Rewrite the following "callback hell" code using both Promises and async/await. Which approach do you find most readable?

```js
// Callback hell version
getUser(userId, function(user) {
  getPosts(user.id, function(posts) {
    getComments(posts[0].id, function(comments) {
      console.log(user.name, posts.length, comments.length);
    });
  });
});
```

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// Promise version
function getUser(userId) {
  return new Promise(resolve => setTimeout(() => resolve({id: userId, name: "User " + userId}), 1000));
}

function getPosts(userId) {
  return new Promise(resolve => setTimeout(() => resolve(["Post 1", "Post 2", "Post 3"]), 1000));
}

function getComments(postId) {
  return new Promise(resolve => setTimeout(() => resolve(["Comment 1", "Comment 2"]), 1000));
}

// Promise chaining approach
getUser(123)
  .then(user => {
    return getPosts(user.id)
      .then(posts => {
        return getComments(posts[0].id)
          .then(comments => {
            console.log(user.name, posts.length, comments.length);
          });
      });
  });

// Better Promise chaining (flatter)
getUser(123)
  .then(user => {
    const userData = user;
    return getPosts(user.id).then(posts => {
      return getComments(posts[0].id).then(comments => {
        console.log(userData.name, posts.length, comments.length);
      });
    });
  });

// async/await approach
async function getUserActivity() {
  const user = await getUser(123);
  const posts = await getPosts(user.id);
  const comments = await getComments(posts[0].id);
  console.log(user.name, posts.length, comments.length);
}

getUserActivity();

// The async/await approach is generally considered most readable as it:
// 1. Looks like synchronous code (easier to understand)
// 2. Eliminates nesting
// 3. Shows clear sequence of operations
// 4. Is more concise
```

</details>

---

## 17. Multiple Promises with async/await
**Question:**  
How would you wait for multiple Promises to complete using async/await?

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
async function getMultipleData() {
  try {
    // Create Promises for different data sources
    const userPromise = fetchUser();
    const postsPromise = fetchPosts();
    const settingsPromise = fetchSettings();
    
    // Wait for all three promises to complete
    const user = await userPromise;
    const posts = await postsPromise;
    const settings = await settingsPromise;
    
    // Use the data once all promises have resolved
    console.log(user, posts, settings);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
}

// An even better approach using Promise.all with async/await:
async function getMultipleDataParallel() {
  try {
    // Wait for all promises to complete in parallel
    const [user, posts, settings] = await Promise.all([
      fetchUser(),
      fetchPosts(),
      fetchSettings()
    ]);
    
    console.log(user, posts, settings);
  } catch (error) {
    // If any promise fails, the catch block will execute
    console.error("One of the requests failed:", error);
  }
}
```

</details>

---

## 18. Converting setTimeout to a Promise
**Question:**  
Create a function called `delay` that returns a Promise which resolves after a specified time in milliseconds.

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
function delay(ms) {
  return new Promise(function(resolve) {
    setTimeout(resolve, ms);
  });
}

// Usage examples:
// With promises
delay(2000)
  .then(function() {
    console.log("2 seconds have passed!");
  });

// With async/await
async function example() {
  console.log("Starting...");
  await delay(2000);
  console.log("2 seconds have passed!");
}

example();
```

</details>

---

## 19. Promisify a Callback Function
**Question:**  
Write a general "promisify" function that converts any callback-based function to a Promise-based one. Assume the callback is always the last argument and follows the Node.js convention (error as first parameter).

<details> <summary>💡 Click to reveal answer</summary> 
  
```js
function promisify(fn) {
  return function(...args) {
    return new Promise(function(resolve, reject) {
      // Add the callback as the last argument
      fn(...args, function(error, result) {
        if (error) {
          reject(error);
        } else {
          resolve(result);
        }
      });
    });
  };
}

// Example usage:
function readFileCallback(path, callback) {
  // Simulate reading a file
  setTimeout(function() {
    if (path === 'valid.txt') {
      callback(null, "File contents");
    } else {
      callback(new Error("File not found"));
    }
  }, 1000);
}

// Create a Promise-based version
const readFilePromise = promisify(readFileCallback);

// Use it
readFilePromise('valid.txt')
  .then(function(contents) {
    console.log("File contents:", contents);
  })
  .catch(function(error) {
    console.error("Error:", error);
  });
```

</details>

---

## 20. What happens when async functions throw errors?
**Question:**  
What happens when an error is thrown inside an async function? How should it be handled?

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// When an error is thrown inside an async function, the Promise returned
// by that function is rejected with that error.

async function processData() {
  throw new Error("Something went wrong");
  return "This will never be reached";
}

// Using Promise syntax:
processData()
  .then(result => {
    console.log("Success:", result);  // This won't execute
  })
  .catch(error => {
    console.error("Caught:", error.message);  // This will execute
  });

// Using async/await syntax:
async function handleProcess() {
  try {
    const result = await processData();
    console.log("Success:", result);  // This won't execute
  } catch (error) {
    console.error("Caught:", error.message);  // This will execute
  }
}

handleProcess();

// Without proper error handling, unhandled Promise rejections can happen:
async function noErrorHandling() {
  const result = await processData();  // This will throw an unhandled rejection
  console.log(result);
}
```

</details>

---

## 21. Promises vs Callbacks for Error Propagation
**Question:**  
Compare how errors propagate in callback-based code versus Promise-based code.

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// In callback-based code:
function operationWithCallback(callback) {
  asyncOperation1(function(err, result1) {
    if (err) {
      return callback(err);  // Need to manually propagate errors
    }
    
    asyncOperation2(result1, function(err, result2) {
      if (err) {
        return callback(err);  // Need to manually propagate errors again
      }
      
      asyncOperation3(result2, function(err, finalResult) {
        if (err) {
          return callback(err);  // And again...
        }
        
        callback(null, finalResult);  // Finally success
      });
    });
  });
}

// In Promise-based code:
function operationWithPromises() {
  return asyncOperation1()
    .then(result1 => asyncOperation2(result1))
    .then(result2 => asyncOperation3(result2));
  // Errors automatically propagate to the next .catch()
}

operationWithPromises()
  .then(finalResult => console.log(finalResult))
  .catch(error => console.error(error));  // All errors are caught here

// Key differences:
// 1. In callbacks, error handling requires explicit checks at each step
// 2. In Promises, errors automatically propagate through the chain
// 3. Without careful coding, callback errors are easy to miss
// 4. Promises provide a single catch point for all errors in the chain
```

</details>

---

## 22. Returning Values from async Functions
**Question:**  
What is always returned from an async function? How do you access the value it returns?

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// An async function always returns a Promise, even if you return a simple value.

async function getName() {
  return "Alice";  // Automatically wrapped in a Promise
}

// Method 1: Using .then() to get the value
getName()
  .then(function(name) {
    console.log("Name is:", name);  // "Name is: Alice"
  });

// Method 2: Using async/await to get the value
async function displayName() {
  const name = await getName();
  console.log("Name is:", name);  // "Name is: Alice"
}

displayName();

// Even returning nothing creates a Promise that resolves to undefined
async function doNothing() {
  // No return statement
}

doNothing().then(result => {
  console.log("Result is:", result);  // "Result is: undefined"
});
```
</details>

---

## 23. Sequential vs Parallel Promise Execution
**Question:**  
Compare sequential execution (one after another) with parallel execution (all at once) of Promises. When would you use each approach?

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// Helper functions that take 1 second each
function task1() {
  return new Promise(resolve => setTimeout(() => {
    console.log("Task 1 complete");
    resolve("Result 1");
  }, 1000));
}

function task2() {
  return new Promise(resolve => setTimeout(() => {
    console.log("Task 2 complete");
    resolve("Result 2");
  }, 1000));
}

function task3() {
  return new Promise(resolve => setTimeout(() => {
    console.log("Task 3 complete");
    resolve("Result 3");
  }, 1000));
}

// Sequential execution (takes ~3 seconds total)
async function sequentialTasks() {
  console.time("Sequential");
  
  const result1 = await task1();
  const result2 = await task2();
  const result3 = await task3();
  
  console.log("All results:", result1, result2, result3);
  console.timeEnd("Sequential");
}

// Parallel execution (takes ~1 second total)
async function parallelTasks() {
  console.time("Parallel");
  
  const promise1 = task1();
  const promise2 = task2();
  const promise3 = task3();
  
  const result1 = await promise1;
  const result2 = await promise2;
  const result3 = await promise3;
  
  console.log("All results:", result1, result2, result3);
  console.timeEnd("Parallel");
}

// Use sequential execution when:
// 1. Each task depends on the result of the previous task
// 2. You need to ensure operations happen in a specific order
// 3. You're rate-limiting requests to an API

// Use parallel execution when:
// 1. Tasks are independent of each other
// 2. You want to minimize total waiting time
// 3. You're fetching multiple resources simultaneously
```

</details>

---
## 24. finally() Method Use Cases
**Question:**  
Give an example of when you would use the `.finally()` method in a Promise chain. What makes it useful?

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// Common use case: loading indicator for data fetching

// Show loading indicator
document.getElementById('loading').style.display = 'block';

fetchData()
  .then(data => {
    // Process the data on success
    displayData(data);
  })
  .catch(error => {
    // Show error message on failure
    showErrorMessage(error);
  })
  .finally(() => {
    // Hide the loading indicator whether the operation succeeded or failed
    document.getElementById('loading').style.display = 'none';
  });

// The finally() method is useful because:
// 1. It runs regardless of success or failure
// 2. Perfect for cleanup operations
// 3. Reduces code duplication (no need to hide the loader in both then() and catch())
// 4. Improves code organization by separating cleanup logic from success/error handling
// 5. Makes sure cleanup happens even if there's an error in the then() block
```

</details>

---

## 25. Converting Callback Hell to async/await
**Question:**  
Convert this "callback hell" code to use async/await to make it more readable:

```js
function getUserData() {
  fetchUser(function(err, user) {
    if (err) {
      console.error("Error fetching user:", err);
      return;
    }
    
    fetchPosts(user.id, function(err, posts) {
      if (err) {
        console.error("Error fetching posts:", err);
        return;
      }
      
      fetchComments(posts[0].id, function(err, comments) {
        if (err) {
          console.error("Error fetching comments:", err);
          return;
        }
        
        displayUserData(user, posts, comments, function(err) {
          if (err) {
            console.error("Error displaying data:", err);
            return;
          }
          
          console.log("Data displayed successfully!");
        });
      });
    });
  });
}
```

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// First, convert the callback-based functions to Promise-based
function fetchUser() {
  return new Promise((resolve, reject) => {
    // Original function implementation here
    setTimeout(() => resolve({id: 123, name: "Alice"}), 1000);
  });
}

function fetchPosts(userId) {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve(["Post 1", "Post 2"]), 1000);
  });
}

function fetchComments(postId) {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve(["Comment 1", "Comment 2"]), 1000);
  });
}

function displayUserData(user, posts, comments) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Displaying:", user, posts, comments);
      resolve();
    }, 1000);
  });
}

// Now use async/await for clean sequential code
async function getUserData() {
  try {
    const user = await fetchUser();
    const posts = await fetchPosts(user.id);
    const comments = await fetchComments(posts[0].id);
    await displayUserData(user, posts, comments);
    console.log("Data displayed successfully!");
  } catch (error) {
    console.error("Error:", error);
  }
}

// Call the function
getUserData();
```

</details>

---

## 26. Promise vs async/await - Error Handling Comparison
**Question:**  
Compare error handling in Promises (.then/.catch) versus async/await (try/catch). Which one do you find clearer?

<details> <summary>💡 Click to reveal answer</summary>  
  
```js
// Promise-based error handling
function promiseBasedFunction() {
  return fetchData()
    .then(data => {
      return processData(data);
    })
    .then(result => {
      return formatResult(result);
    })
    .catch(error => {
      console.error("An error occurred:", error);
      return defaultResult();
    });
}

// async/await-based error handling
async function asyncAwaitFunction() {
  try {
    const data = await fetchData();
    const result = await processData(data);
    return await formatResult(result);
  } catch (error) {
    console.error("An error occurred:", error);
    return defaultResult();
  }
}

// Comparison:
// 1. async/await with try/catch is generally clearer because:
//    - It follows familiar synchronous code patterns
//    - The error handling block is separate from the "happy path" code
//    - There's less nesting and indentation
//    - It's easier to see which operations are inside the error handling scope
//
// 2. Promise .catch() advantages:
//    - Can be more flexible for complex chains
//    - Can have multiple .catch() handlers for different parts of the chain
//    - Better for functional programming approaches
```

</details>

---

## 27. When to use callbacks vs Promises vs async/await
**Question:**  
In what situations would you still use callbacks instead of Promises or async/await in modern JavaScript code?

<details> <summary>💡 Click to reveal answer</summary>  
  
```
When to use callbacks vs Promises vs async/await:

Callbacks are still appropriate for:
1. Event listeners (e.g., click, mouseover)
2. Simple non-nested asynchronous operations
3. When working with APIs that are callback-based (e.g., older Node.js APIs)
4. When using libraries that expect callback functions
5. For higher-order functions like array methods (map, filter, reduce)

Use Promises when:
1. Working with multiple asynchronous operations that need coordination
2. Handling success and error cases separately
3. Transforming or chaining asynchronous results
4. Working with APIs that already return Promises

Use async/await when:
1. Writing complex asynchronous logic with conditional flows
2. Need maximum readability for asynchronous code
3. Handling errors with try/catch blocks
4. When the code structure benefits from a more synchronous-looking approach
5. Working with many sequential asynchronous operations
```

</details>

---

## 28. Promises and the Event Loop
**Question:**  
Explain how Promises work with JavaScript's event loop. What happens when a Promise resolves?

<details> <summary>💡 Click to reveal answer</summary>  
  
```
How Promises work with the event loop:

1. When a Promise is created, its executor function runs synchronously.

2. When async operations inside the executor complete, their callbacks are added to the "microtask queue" in the event loop.

3. Microtasks have higher priority than regular tasks (like setTimeout callbacks).

4. When a Promise resolves:
   - Its state changes from pending to fulfilled
   - The value it resolves with is stored
   - All attached .then() callbacks are queued as microtasks

5. After the current synchronous code completes, the event loop processes the microtask queue before regular tasks.

6. This means Promise callbacks run before setTimeout or setInterval callbacks, even if the timeout is set to 0.

Example of execution order:

console.log("1. Synchronous code");

setTimeout(() => {
  console.log("4. Timeout callback (regular task)");
}, 0);

Promise.resolve()
  .then(() => console.log("3. Promise callback (microtask)"));

console.log("2. More synchronous code");

// Output:
// 1. Synchronous code
// 2. More synchronous code
// 3. Promise callback (microtask)
// 4. Timeout callback (regular task)
```

</details>

---

