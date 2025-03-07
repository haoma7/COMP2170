# JavaScript Array Exercises

## 1. **Array Literals**

**Exercise 1.1:** Create an array literal containing your five favorite foods.

**Expected Answer:**
```javascript
const favoriteFoods = ["pizza", "sushi", "chocolate", "tacos", "ice cream"];
```

**Exercise 1.2:** Create a nested array representing a tic-tac-toe board with 'X' in the center.

**Expected Answer:**
```javascript
const ticTacToe = [
  [null, null, null],
  [null, 'X', null],
  [null, null, null]
];
```

## 2. **Spread Operator**

**Exercise 2.1:** Combine two arrays `[1, 2, 3]` and `[4, 5, 6]` using the spread operator.

**Expected Answer:**
```javascript
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const combined = [...arr1, ...arr2]; // [1, 2, 3, 4, 5, 6]
```

**Exercise 2.2:** Make a copy of an array and add a new element to the copy without modifying the original.

**Expected Answer:**
```javascript
const original = ['a', 'b', 'c'];
const copy = [...original, 'd']; // ['a', 'b', 'c', 'd']
console.log(original); // ['a', 'b', 'c'] (unchanged)
```

**Exercise 2.3:** Use the spread operator to insert the elements of array `[3, 4]` between the elements of array `[1, 2]` and `[5, 6]`.

**Expected Answer:**
```javascript
const part1 = [1, 2];
const middle = [3, 4];
const part2 = [5, 6];
const result = [...part1, ...middle, ...part2]; // [1, 2, 3, 4, 5, 6]
```

## 3. **Array Constructor**

**Exercise 3.1:** Create an array of length 5 with all elements undefined using the Array constructor.

**Expected Answer:**
```javascript
const arr = new Array(5);
console.log(arr.length); // 5
console.log(arr); // [empty × 5]
```

**Exercise 3.2:** Create an array containing the numbers 1, 2, and 3 using the Array constructor.

**Expected Answer:**
```javascript
const arr = new Array(1, 2, 3);
console.log(arr); // [1, 2, 3]
```

**Exercise 3.3:** What's the difference between `new Array(3)` and `new Array(1, 2, 3)`? Explain.

**Expected Answer:**
```javascript
// new Array(3) creates an array with length 3 but no defined elements (sparse array)
const arr1 = new Array(3);
console.log(arr1); // [empty × 3]

// new Array(1, 2, 3) creates an array with 3 elements with values 1, 2, and 3
const arr2 = new Array(1, 2, 3);
console.log(arr2); // [1, 2, 3]

// The key difference is that when the Array constructor receives a single numeric argument,
// it creates an empty array with that length. When it receives multiple arguments,
// those arguments become the elements of the new array.
```

## 4. **Array.of()**

**Exercise 4.1:** Create an array containing a single number 5 using `Array.of()`.

**Expected Answer:**
```javascript
const arr = Array.of(5);
console.log(arr); // [5]
```

**Exercise 4.2:** Compare the result of `Array.of(3)` and `new Array(3)`. What's the difference?

**Expected Answer:**
```javascript
const arr1 = Array.of(3);
const arr2 = new Array(3);

console.log(arr1); // [3] (array with one element, the number 3)
console.log(arr2); // [empty × 3] (array with length 3 but no actual elements)
```

**Exercise 4.3:** Create an array with `Array.of()` containing different types of data: a number, a string, a boolean, and an object.

**Expected Answer:**
```javascript
const mixedArray = Array.of(42, "hello", true, { name: "JavaScript" });
console.log(mixedArray); // [42, "hello", true, { name: "JavaScript" }]
```

## 5. **Array.from()**

**Exercise 5.1:** Convert a string to an array of characters using `Array.from()`.

**Expected Answer:**
```javascript
const str = "hello";
const charArray = Array.from(str);
console.log(charArray); // ["h", "e", "l", "l", "o"]
```
**Any other ways to solve this problem without `Array.from()`?**

**Exercise 5.2:** How can you create a new array with the elements [0, 1, 2, 3, 4] by doubling each element in the array using Array.from()?

**Expected Answer:**
```javascript
const arr = Array.from([0, 1, 2, 3, 4], x => x * 2);
console.log(arr); // [0, 2, 4, 6, 8]
```

## 6. **Array.isArray()**

**Exercise 6.1:** Check which of the following variables are arrays using `Array.isArray()`:
```javascript
const a = [1, 2, 3];
const b = "123";
const c = { length: 3 };
const d = Array.from("123");
```

**Expected Answer:**
```javascript
console.log(Array.isArray(a)); // true
console.log(Array.isArray(b)); // false
console.log(Array.isArray(c)); // false
console.log(Array.isArray(d)); // true
```

**Exercise 6.2:** Why doesn't `typeof` work for detecting arrays? Write code to demonstrate and explain.

**Expected Answer:**
```javascript
const arr = [1, 2, 3];
console.log(typeof arr); // "object"

// Explanation: typeof returns "object" for arrays because in JavaScript,
// arrays are a special type of object. This is why we need Array.isArray()
// to specifically check if something is an array.

console.log(Array.isArray(arr)); // true - correctly identifies as an array
```

## 7. **Reading Array Elements**

**Exercise 7.1:** Access the third element in the array `["apple", "banana", "cherry", "date", "elderberry"]`.

**Expected Answer:**
```javascript
const fruits = ["apple", "banana", "cherry", "date", "elderberry"];
const thirdFruit = fruits[2]; // "cherry"
console.log(thirdFruit);
```

**Exercise 7.2:** Access the last element of an array without knowing its length.

**Expected Answer:**
```javascript
const animals = ["dog", "cat", "bird", "fish"];
const lastAnimal = animals[animals.length - 1]; // "fish"
console.log(lastAnimal);
```

**Exercise 7.3:** What is returned when you try to access an element at an index that doesn't exist?

**Expected Answer:**
```javascript
const numbers = [10, 20, 30];
console.log(numbers[5]); // undefined
// Attempting to access an element at an index that doesn't exist returns undefined
```

## 8. **Writing Array Elements**

**Exercise 8.1:** Create an empty array and then add elements at indexes 0, 1, and 2.

**Expected Answer:**
```javascript
const arr = [];
arr[0] = "first";
arr[1] = "second";
arr[2] = "third";
console.log(arr); // ["first", "second", "third"]
```

**Exercise 8.2:** What happens if you write to an array at an index past its current length? Demonstrate.

**Expected Answer:**
```javascript
const arr = [1, 2, 3];
arr[7] = 8;
console.log(arr); // [1, 2, 3, empty × 4, 8]
console.log(arr.length); // 8
// When writing to an index past the array's length, the array is extended
// and empty slots are created for the missing indexes
```

**Exercise 8.3:** Modify the second element of array `["red", "green", "blue"]` to be "yellow".

**Expected Answer:**
```javascript
const colors = ["red", "green", "blue"];
colors[1] = "yellow";
console.log(colors); // ["red", "yellow", "blue"]
```

## 9. **Array Length**

**Exercise 9.1:** Create an array with 5 elements and then make it empty by setting its length to 0.

**Expected Answer:**
```javascript
const arr = [1, 2, 3, 4, 5];
arr.length = 0;
console.log(arr); // []
```

**Exercise 9.2:** What happens when you set the length of an array to a value less than its current length? Demonstrate.

**Expected Answer:**
```javascript
const arr = ["a", "b", "c", "d", "e"];
arr.length = 3;
console.log(arr); // ["a", "b", "c"]
// Setting length to a smaller value truncates the array, removing elements at the end
```

**Exercise 9.3:** Create an array and extend its length by setting the `length` property. What are the values of the new elements?

**Expected Answer:**
```javascript
const arr = [1, 2, 3];
arr.length = 6;
console.log(arr); // [1, 2, 3, empty × 3]
console.log(arr[4]); // undefined
// When extending an array by setting length, the new slots are empty (undefined when accessed)
```

## 10. **push() Method**

**Exercise 10.1:** Add the elements 4, 5, and 6 to the array `[1, 2, 3]` using a single `push()` call.

**Expected Answer:**
```javascript
const numbers = [1, 2, 3];
numbers.push(4, 5, 6);
console.log(numbers); // [1, 2, 3, 4, 5, 6]
```

**Exercise 10.2:** What is the return value of the `push()` method? Demonstrate.

**Expected Answer:**
```javascript
const arr = ["a", "b"];
const result = arr.push("c", "d");
console.log(result); // 4
console.log(arr); // ["a", "b", "c", "d"]
// push() returns the new length of the array after adding the elements
```

**Exercise 10.3:** Push all elements from one array to another using the spread operator.

**Expected Answer:**
```javascript
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
arr1.push(...arr2);
console.log(arr1); // [1, 2, 3, 4, 5, 6]
```

## 11. **pop() Method**

**Exercise 11.1:** Remove the last element from the array `[10, 20, 30, 40]` using `pop()` and store the removed element in a variable.

**Expected Answer:**
```javascript
const numbers = [10, 20, 30, 40];
const removed = numbers.pop();
console.log(removed); // 40
console.log(numbers); // [10, 20, 30]
```

**Exercise 11.2:** What does `pop()` return when called on an empty array?

**Expected Answer:**
```javascript
const emptyArr = [];
const result = emptyArr.pop();
console.log(result); // undefined
// pop() returns undefined when called on an empty array
```

**Exercise 11.3:** Implement a simple stack (LIFO - Last In, First Out) using only `push()` and `pop()` methods.

**Expected Answer:**
```javascript
class Stack {
  constructor() {
    this.items = [];
  }
  
  push(element) {
    this.items.push(element);
  }
  
  pop() {
    return this.items.pop();
  }
  
  peek() {
    return this.items[this.items.length - 1];
  }
  
  isEmpty() {
    return this.items.length === 0;
  }
  
  size() {
    return this.items.length;
  }
}

// Usage
const stack = new Stack();
stack.push("first");
stack.push("second");
console.log(stack.pop()); // "second"
console.log(stack.peek()); // "first"
```

## 12. **unshift() Method**

**Exercise 12.1:** Add elements "one" and "two" to the beginning of the array `["three", "four"]` using `unshift()`.

**Expected Answer:**
```javascript
const arr = ["three", "four"];
arr.unshift("one", "two");
console.log(arr); // ["one", "two", "three", "four"]
```

**Exercise 12.2:** What is the return value of `unshift()`? Demonstrate.

**Expected Answer:**
```javascript
const arr = ["c", "d"];
const result = arr.unshift("a", "b");
console.log(result); // 4
console.log(arr); // ["a", "b", "c", "d"]
// unshift() returns the new length of the array after adding the elements
```

**Exercise 12.3:** Compare the performance considerations of using `unshift()` versus `push()`.

**Expected Answer:**
```javascript
// Performance Demonstration
const smallArray = [3, 4, 5];
const largeArray = new Array(1000000).fill(0);

// For small arrays, the difference is negligible
console.time('small-push');
smallArray.push(6);
console.timeEnd('small-push');

console.time('small-unshift');
smallArray.unshift(2);
console.timeEnd('small-unshift');

// For large arrays, unshift is much slower than push
console.time('large-push');
largeArray.push(1);
console.timeEnd('large-push');

console.time('large-unshift');
largeArray.unshift(1);
console.timeEnd('large-unshift');

/* Expected result:
unshift() is significantly slower than push() for large arrays because:
- push() only needs to add an element at the end
- unshift() needs to shift all existing elements to new positions,
  which is an O(n) operation where n is the array length
*/
```

## 13. **shift() Method**

**Exercise 13.1:** Remove the first element from the array `["apple", "banana", "cherry"]` using `shift()`.

**Expected Answer:**
```javascript
const fruits = ["apple", "banana", "cherry"];
const removed = fruits.shift();
console.log(removed); // "apple"
console.log(fruits); // ["banana", "cherry"]
```

**Exercise 13.2:** What does `shift()` return when called on an empty array?

**Expected Answer:**
```javascript
const emptyArr = [];
const result = emptyArr.shift();
console.log(result); // undefined
// shift() returns undefined when called on an empty array
```

**Exercise 13.3:** Implement a simple queue (FIFO - First In, First Out) using only `push()` and `shift()`.

**Expected Answer:**
```javascript
class Queue {
  constructor() {
    this.items = [];
  }
  
  enqueue(element) {
    this.items.push(element);
  }
  
  dequeue() {
    return this.items.shift();
  }
  
  front() {
    return this.items[0];
  }
  
  isEmpty() {
    return this.items.length === 0;
  }
  
  size() {
    return this.items.length;
  }
}

// Usage
const queue = new Queue();
queue.enqueue("first");
queue.enqueue("second");
console.log(queue.dequeue()); // "first"
console.log(queue.front()); // "second"
```

## 14. **delete Operator**

**Exercise 14.1:** Remove the second element from the array `[1, 2, 3, 4]` using the `delete` operator. What does the resulting array look like?

**Expected Answer:**
```javascript
const arr = [1, 2, 3, 4];
delete arr[1];
console.log(arr); // [1, empty, 3, 4]
console.log(arr.length); // 4
// delete removes the value but keeps the slot (creates a "hole"), maintaining the array length
```

**Exercise 14.2:** Compare using `delete` versus `splice()` for removing an array element.

**Expected Answer:**
```javascript
// Using delete
const arr1 = [1, 2, 3, 4, 5];
delete arr1[2];
console.log(arr1); // [1, 2, empty, 4, 5]
console.log(arr1.length); // 5

// Using splice
const arr2 = [1, 2, 3, 4, 5];
arr2.splice(2, 1);
console.log(arr2); // [1, 2, 4, 5]
console.log(arr2.length); // 4

/* Comparison:
1. delete sets the element to undefined but keeps its position, leaving a "hole"
2. splice() removes the element completely and shifts subsequent elements
3. delete doesn't change the array length, splice() reduces the length
4. splice() is generally more useful for most array operations
*/
```

## 15. **for-of Loop**

**Exercise 15.1:** Use a `for-of` loop to sum all numbers in the array `[10, 20, 30, 40, 50]`.

**Expected Answer:**
```javascript
const numbers = [10, 20, 30, 40, 50];
let sum = 0;

for (const num of numbers) {
  sum += num;
}

console.log(sum); // 150
```

**Exercise 15.2:** Use a `for-of` loop to create a new array containing the squares of the numbers in the array `[1, 2, 3, 4, 5]`.

**Expected Answer:**
```javascript
const numbers = [1, 2, 3, 4, 5];
const squares = [];

for (const num of numbers) {
  squares.push(num ** 2);
}

console.log(squares); // [1, 4, 9, 16, 25]
```

**Exercise 15.3:** Does `for-of` work on sparse arrays? Demonstrate with an example.

**Expected Answer:**
```javascript
const sparseArray = [1, , 3, , 5];
const values = [];

for (const value of sparseArray) {
  values.push(value);
}

console.log(values); // [1, undefined, 3, undefined, 5]
// for-of does work on sparse arrays, but it treats empty slots as undefined
```

**Exercise 15.4:** How can you get both the index and value in a `for-of` loop? Demonstrate.

**Expected Answer:**
```javascript
const fruits = ["apple", "banana", "cherry"];

for (const [index, fruit] of fruits.entries()) {
  console.log(`${index}: ${fruit}`);
}
// Output:
// 0: apple
// 1: banana
// 2: cherry
```

## 16. **forEach() Method**

**Exercise 16.1:** Use `forEach()` to capitalize each string in the array `["apple", "banana", "cherry"]`.

**Expected Answer:**
```javascript
const fruits = ["apple", "banana", "cherry"];
const capitalized = [];

fruits.forEach(fruit => {
  capitalized.push(fruit.charAt(0).toUpperCase() + fruit.slice(1));
});

console.log(capitalized); // ["Apple", "Banana", "Cherry"]
```

**Exercise 16.2:** What are the arguments provided to the callback function in `forEach()`? Demonstrate each.

**Expected Answer:**
```javascript
const arr = ["a", "b", "c"];

arr.forEach((value, index, array) => {
  console.log(`Value: ${value}`);
  console.log(`Index: ${index}`);
  console.log(`Array: ${array}`);
  console.log('---');
});

// Output:
// Value: a
// Index: 0
// Array: a,b,c
// ---
// Value: b
// Index: 1
// Array: a,b,c
// ---
// Value: c
// Index: 2
// Array: a,b,c
// ---
```

**Exercise 16.3:** Can you break out of a `forEach()` loop early? If not, what alternatives do you have?

**Expected Answer:**
```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

console.log("Using forEach (can't break):");
try {
  numbers.forEach(num => {
    console.log(num);
    if (num === 5) {
      // This won't actually break the loop
      throw new Error("Breaking forEach");
    }
  });
} catch (e) {
  console.log("Caught:", e.message);
}

console.log("\nAlternative 1: Using for...of (can break):");
for (const num of numbers) {
  console.log(num);
  if (num === 5) break;
}

console.log("\nAlternative 2: Using some() (can short-circuit):");
numbers.some(num => {
  console.log(num);
  return num === 5; // Returns true for 5, causing some() to stop
});

console.log("\nAlternative 3: Using every() (can short-circuit):");
numbers.every(num => {
  console.log(num);
  return num !== 5; // Returns false for 5, causing every() to stop
});

/* Explanation:
   You cannot break out of forEach() normally. Alternatives include:
   1. Using try/catch with throw (not recommended)
   2. Using for...of instead (which supports break)
   3. Using Array.some() which stops when callback returns true
   4. Using Array.every() which stops when callback returns false
*/
```

## 17. **map() Method**

**Exercise 17.1:** Use `map()` to convert an array of Celsius temperatures `[0, 10, 20, 30, 40]` to Fahrenheit.

**Expected Answer:**
```javascript
const celsius = [0, 10, 20, 30, 40];
const fahrenheit = celsius.map(temp => (temp * 9/5) + 32);
console.log(fahrenheit); // [32, 50, 68, 86, 104]
```

**Exercise 17.2:** Use `map()` to extract a specific property from each object in an array.

**Expected Answer:**
```javascript
const users = [
  { id: 1, name: "Alice", age: 25 },
  { id: 2, name: "Bob", age: 30 },
  { id: 3, name: "Charlie", age: 35 }
];

const names = users.map(user => user.name);
console.log(names); // ["Alice", "Bob", "Charlie"]
```

**Exercise 17.3:** When might you use `map()` versus `forEach()`? What's the key difference?

**Expected Answer:**
```javascript
// map() creates a new array with transformed values
const numbers = [1, 2, 3];
const doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6]
console.log(numbers); // [1, 2, 3] (original unchanged)

// forEach() doesn't return anything, it just executes a function on each element
let sum = 0;
numbers.forEach(num => {
  sum += num;
});
console.log(sum); // 6

/* Key differences:
   1. map() returns a new array, forEach() returns undefined
   2. map() is for transforming elements into new values
   3. forEach() is for performing operations with side effects
   4. map() maintains array length and structure, creating a 1:1 mapping
   5. Using map() for side effects (without using its return value) is considered bad practice
*/
```

## 18. **filter() Method**

**Exercise 18.1:** Filter out all odd numbers from the array `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`.

**Expected Answer:**
```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const evens = numbers.filter(num => num % 2 === 0);
console.log(evens); // [2, 4, 6, 8, 10]
```

**Exercise 18.2:** Filter an array of objects to only include users who are 18 or older.

**Expected Answer:**
```javascript
const users = [
  { name: "Alice", age: 21 },
  { name: "Bob", age: 17 },
  { name: "Charlie", age: 25 },
  { name: "David", age: 16 }
];

const adults = users.filter(user => user.age >= 18);
console.log(adults); 
// [{ name: "Alice", age: 21 }, { name: "Charlie", age: 25 }]
```

**Exercise 18.3:** Remove all falsy values (`false`, `null`, `0`, `""`, `undefined`, and `NaN`) from an array.

**Expected Answer:**
```javascript
const mixedValues = [0, 1, false, true, "", "hello", undefined, null, NaN, 42];
const truthyValues = mixedValues.filter(Boolean);
console.log(truthyValues); // [1, true, "hello", 42]

// Alternative explicit version:
const truthyExplicit = mixedValues.filter(value => !!value);
console.log(truthyExplicit); // [1, true, "hello", 42]
```

## 19. **find() Method**

**Exercise 19.1:** Find the first number greater than 5 in the array `[1, 3, 5, 7, 9]`.

**Expected Answer:**
```javascript
const numbers = [1, 3, 5, 7, 9];
const firstGreaterThanFive = numbers.find(num => num > 5);
console.log(firstGreaterThanFive); // 7
```

**Exercise 19.2:** Find a user by their ID in an array of user objects.

**Expected Answer:**
```javascript
const users = [
  { id: 1, name: "Alice" },
  { id: 2, name: "Bob" },
  { id: 3, name: "Charlie" }
];

const userWithId2 = users.find(user => user.id === 2);
console.log(userWithId2); // { id: 2, name: "Bob" }
```

**Exercise 19.3:** What does `find()` return if no element satisfies the condition?

**Expected Answer:**
```javascript
const numbers = [1, 2, 3, 4, 5];
const greaterThanTen = numbers.find(num => num > 10);
console.log(greaterThanTen); // undefined
// find() returns undefined if no element matches the condition
```

**Exercise 19.4:** Compare `find()` with `filter()`. When would you use one over the other?

**Expected Answer:**
```javascript
const numbers = [5, 10, 15, 20, 25];

// find() returns the first matching element (or undefined)
const firstOverTen = numbers.find(num => num > 10);
console.log(firstOverTen); // 15

// filter() returns all matching elements (or an empty array)
const allOverTen = numbers.filter(num => num > 10);
console.log(allOverTen); // [15, 20, 25]

/* When to use which:
   1. Use find() when you only need the first matching element
   2. Use find() when you're looking for a specific unique item (like by ID)
   3. Use filter() when you need all elements that match a condition
   4. find() stops once it finds a match, so it can be more efficient for large arrays
   5. find() returns undefined for no matches, filter() returns an empty array
*/
```

## 20. **findIndex() Method**

**Exercise 20.1:** Find the index of the first number greater than 7 in the array `[2, 4, 6, 8, 10]`.

**Expected Answer:**
```javascript
const numbers = [2, 4, 6, 8, 10];
const index = numbers.findIndex(num => num > 7);
console.log(index); // 3 (since 8 is at index 3)
```

**Exercise 20.2:** What does `findIndex()` return if no element satisfies the condition?

**Expected Answer:**
```javascript
const numbers = [1, 2, 3, 4, 5];
const index = numbers.findIndex(num => num > 10);
console.log(index); // -1
// findIndex() returns -1 if no element matches the condition
```

**Exercise 20.3:** Find the index of a specific product in an array, then use that index to update the product.

**Expected Answer:**
```javascript
const products = [
  { id: 101, name: "Laptop", price: 999 },
  { id: 102, name: "Phone", price: 699 },
  { id: 103, name: "Tablet", price: 399 }
];

// Find the index of the Phone
const phoneIndex = products.findIndex(product => product.id === 102);
console.log(phoneIndex); // 1

// Update the price of the Phone
if (phoneIndex !== -1) {
  products[phoneIndex].price = 649;
}

console.log(products);
// [
//   { id: 101, name: "Laptop", price: 999 },
//   { id: 102, name: "Phone", price: 649 },
//   { id: 103, name: "Tablet", price: 399 }
// ]
```

## 21. **every() Method**

**Exercise 21.1:** Check if all numbers in the array `[2, 4, 6, 8, 10]` are even.

**Expected Answer:**
```javascript
const numbers = [2, 4, 6, 8, 10];
const allEven = numbers.every(num => num % 2 === 0);
console.log(allEven); // true
```

**Exercise 21.2:** Check if all users in an array are adults (18 or older).

**Expected Answer:**
```javascript
const users = [
  { name: "Alice", age: 21 },
  { name: "Bob", age: 19 },
  { name: "Charlie", age: 16 }
];

const allAdults = users.every(user => user.age >= 18);
console.log(allAdults); // false (Charlie is under 18)
```


**Exercise 21.3:** What value does `every()` return for an empty array?

**Expected Answer:**
```javascript
const emptyArray = [];
const result = emptyArray.every(item => item > 0);
console.log(result); // true
// For an empty array, every() returns true (vacuously true)
```

**Exercise 21.4:** Compare the behavior of `every()` and `some()` methods with examples.

**Expected Answer:**
```javascript
const numbers = [1, 3, 5, 8, 9];

// every() returns true only if ALL elements satisfy the condition
const allEven = numbers.every(num => num % 2 === 0);
console.log(allEven); // false (not all numbers are even)

// some() returns true if AT LEAST ONE element satisfies the condition
const someEven = numbers.some(num => num % 2 === 0);
console.log(someEven); // true (8 is even)

// For an empty array:
const empty = [];
console.log(empty.every(num => num > 0)); // true (vacuously true)
console.log(empty.some(num => num > 0));  // false (no elements satisfy)
```

## 22. **some() Method**

**Exercise 22.1:** Check if the array `[1, 3, 5, 7, 9]` contains any even numbers.

**Expected Answer:**
```javascript
const numbers = [1, 3, 5, 7, 9];
const hasEven = numbers.some(num => num % 2 === 0);
console.log(hasEven); // false
```

**Exercise 22.2:** Check if there's at least one admin user in an array of users.

**Expected Answer:**
```javascript
const users = [
  { name: "Alice", role: "user" },
  { name: "Bob", role: "user" },
  { name: "Charlie", role: "admin" }
];

const hasAdmin = users.some(user => user.role === "admin");
console.log(hasAdmin); // true
```

**Exercise 22.3:** What value does `some()` return for an empty array?

**Expected Answer:**
```javascript
const emptyArray = [];
const result = emptyArray.some(item => item > 0);
console.log(result); // false
// For an empty array, some() returns false
```

**Exercise 22.4:** Use `some()` to check if an array contains a specific value.

**Expected Answer:**
```javascript
const fruits = ["apple", "banana", "cherry", "date"];

// Check if "banana" is in the array
const hasBanana = fruits.some(fruit => fruit === "banana");
console.log(hasBanana); // true

// Check if "grape" is in the array
const hasGrape = fruits.some(fruit => fruit === "grape");
console.log(hasGrape); // false
```

## 23. **reduce() Method**

**Exercise 23.1:** Use `reduce()` to sum all numbers in the array `[1, 2, 3, 4, 5]`.

**Expected Answer:**
```javascript
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((total, current) => total + current, 0);
console.log(sum); // 15
```

**Exercise 23.2:** Use `reduce()` to find the maximum value in an array of numbers.

**Expected Answer:**
```javascript
const numbers = [5, 20, 10, 30, 15];
const max = numbers.reduce((max, current) => current > max ? current : max, numbers[0]);
console.log(max); // 30
```

**Exercise 23.3:** Use `reduce()` to convert an array of objects into an object indexed by a specific property.

**Expected Answer:**
```javascript
const users = [
  { id: 1, name: "Alice" },
  { id: 2, name: "Bob" },
  { id: 3, name: "Charlie" }
];

const userMap = users.reduce((acc, user) => {
  acc[user.id] = user;
  return acc;
}, {});

console.log(userMap);
/* Output:
{
  1: { id: 1, name: "Alice" },
  2: { id: 2, name: "Bob" },
  3: { id: 3, name: "Charlie" }
}
*/
```

**Exercise 23.4:** Use `reduce()` to count the frequency of elements in an array.

**Expected Answer:**
```javascript
const fruits = ["apple", "banana", "apple", "orange", "banana", "apple"];

const fruitCount = fruits.reduce((count, fruit) => {
  count[fruit] = (count[fruit] || 0) + 1;
  return count;
}, {});

console.log(fruitCount);
// { apple: 3, banana: 2, orange: 1 }
```

**Exercise 23.5:** Implement a `map()` function using `reduce()`.

**Expected Answer:**
```javascript
const numbers = [1, 2, 3, 4, 5];

// Custom map using reduce
const double = numbers.reduce((acc, current) => {
  acc.push(current * 2);
  return acc;
}, []);

console.log(double); // [2, 4, 6, 8, 10]
```

## 24. **flat() Method**

**Exercise 24.1:** Flatten a nested array `[1, [2, 3], [4, [5, 6]]]` to a single level.

**Expected Answer:**
```javascript
const nested = [1, [2, 3], [4, [5, 6]]];
const flattened = nested.flat(2);
console.log(flattened); // [1, 2, 3, 4, 5, 6]
```

**Exercise 24.2:** What happens when you call `flat()` without arguments? What is the default depth?

**Expected Answer:**
```javascript
const nested = [1, [2, 3], [4, [5, 6]]];
const defaultFlattened = nested.flat();
console.log(defaultFlattened); // [1, 2, 3, 4, [5, 6]]
// The default depth is 1, so only one level of nesting is flattened
```

**Exercise 24.3:** How would you use `flat()` to flatten an array with unknown nesting depth?

**Expected Answer:**
```javascript
const deeplyNested = [1, [2, [3, [4, [5, [6]]]]]];
const completelyFlat = deeplyNested.flat(Infinity);
console.log(completelyFlat); // [1, 2, 3, 4, 5, 6]
// Using Infinity as the depth parameter flattens all nesting levels
```

## 25. **flatMap() Method**

**Exercise 25.1:** Use `flatMap()` to create an array of words from an array of sentences.

**Expected Answer:**
```javascript
const sentences = ["Hello world", "This is JavaScript", "Arrays are fun"];
const words = sentences.flatMap(sentence => sentence.split(" "));
console.log(words);
// ["Hello", "world", "This", "is", "JavaScript", "Arrays", "are", "fun"]
```

**Exercise 25.2:** Compare using `map()` followed by `flat()` versus using `flatMap()` directly.

**Expected Answer:**
```javascript
const numbers = [1, 2, 3];

// Using map() and flat() separately
const mapThenFlat = numbers.map(num => [num, num * 2]).flat();
console.log(mapThenFlat); // [1, 2, 2, 4, 3, 6]

// Using flatMap() directly
const flatMapped = numbers.flatMap(num => [num, num * 2]);
console.log(flatMapped); // [1, 2, 2, 4, 3, 6]

// Performance comparison
console.time('map-then-flat');
for(let i = 0; i < 1000; i++) {
  numbers.map(num => [num, num * 2]).flat();
}
console.timeEnd('map-then-flat');

console.time('flatMap');
for(let i = 0; i < 1000; i++) {
  numbers.flatMap(num => [num, num * 2]);
}
console.timeEnd('flatMap');

/* Expected result:
   flatMap() is generally more efficient than using map() and flat() separately
   because it only iterates over the array once.
*/
```

**Exercise 25.3:** Use `flatMap()` to filter and transform elements at the same time.

**Expected Answer:**
```javascript
const numbers = [1, 2, 3, 4, 5];

// Get squares of even numbers only
const evenSquares = numbers.flatMap(num => 
  num % 2 === 0 ? [num * num] : []
);

console.log(evenSquares); // [4, 16]

/* Explanation:
   This example shows how flatMap() can combine filtering and mapping:
   - For even numbers, we return an array with one element (the square)
   - For odd numbers, we return an empty array (which gets flattened away)
   - The result is only the squares of even numbers
*/
```

## 26. **concat() Method**

**Exercise 26.1:** Merge the arrays `[1, 2, 3]`, `[4, 5]`, and `[6]` into a single array.

**Expected Answer:**
```javascript
const arr1 = [1, 2, 3];
const arr2 = [4, 5];
const arr3 = [6];

const merged = arr1.concat(arr2, arr3);
console.log(merged); // [1, 2, 3, 4, 5, 6]
```

**Exercise 26.2:** Does `concat()` modify the original array? Demonstrate.

**Expected Answer:**
```javascript
const original = [1, 2, 3];
const addition = [4, 5];
const result = original.concat(addition);

console.log(original); // [1, 2, 3] (unchanged)
console.log(addition); // [4, 5] (unchanged)
console.log(result);   // [1, 2, 3, 4, 5]

// concat() returns a new array without modifying the originals
```

**Exercise 26.3:** Compare using `concat()` versus the spread operator for combining arrays.

**Expected Answer:**
```javascript
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

// Using concat()
const method1 = arr1.concat(arr2);
console.log(method1); // [1, 2, 3, 4, 5, 6]

// Using spread operator
const method2 = [...arr1, ...arr2];
console.log(method2); // [1, 2, 3, 4, 5, 6]

/* Comparison:
   1. Both methods create a new array without modifying the originals
   2. Spread operator is often considered more readable for simple concatenation
   3. concat() can be chained with other array methods
   4. concat() has slightly better browser compatibility for older browsers
   5. concat() can handle non-array arguments too (they're added as elements)
*/

// Non-array argument example
const withExtra = arr1.concat(arr2, 7, 8);
console.log(withExtra); // [1, 2, 3, 4, 5, 6, 7, 8]
```

## 27. **slice() Method**

**Exercise 27.1:** Extract elements from index 2 to 4 (exclusive) from the array `[10, 20, 30, 40, 50]`.

**Expected Answer:**
```javascript
const numbers = [10, 20, 30, 40, 50];
const sliced = numbers.slice(2, 4);
console.log(sliced); // [30, 40]
```

**Exercise 27.2:** What does `slice()` return when given negative indices? Demonstrate.

**Expected Answer:**
```javascript
const letters = ["a", "b", "c", "d", "e"];

// Negative start index counts from the end
const fromEnd = letters.slice(-2);
console.log(fromEnd); // ["d", "e"] (last 2 elements)

// Negative start and end indices
const negativeRange = letters.slice(-4, -1);
console.log(negativeRange); // ["b", "c", "d"] (from 4th last to 1st last, exclusive)
```

**Exercise 27.3:** Create a function that returns the last n elements of an array using `slice()`.

**Expected Answer:**
```javascript
function lastN(array, n) {
  return array.slice(-n);
}

const numbers = [10, 20, 30, 40, 50];
console.log(lastN(numbers, 3)); // [30, 40, 50]
console.log(lastN(numbers, 1)); // [50]
console.log(lastN(numbers, 0)); // []
```

**Exercise 27.4:** Create a function that creates a shallow copy of an array using `slice()`.

**Expected Answer:**
```javascript
function shallowCopy(array) {
  return array.slice();
}

const original = [1, 2, 3, { name: "JavaScript" }];
const copy = shallowCopy(original);

console.log(copy); // [1, 2, 3, { name: "JavaScript" }]
console.log(copy === original); // false (different array instances)

// Demonstrate shallow copy behavior
copy[0] = 100;
copy[3].name = "Modified";

console.log(original); // [1, 2, 3, { name: "Modified" }]
console.log(copy);     // [100, 2, 3, { name: "Modified" }]

// The primitive values were copied, but the object reference is shared
```

## 28. **splice() Method**

**Exercise 28.1:** Remove 2 elements starting from index 1 from the array `[10, 20, 30, 40, 50]` and replace them with the values 25 and 35.

**Expected Answer:**
```javascript
const numbers = [10, 20, 30, 40, 50];
const removed = numbers.splice(1, 2, 25, 35);

console.log(removed); // [20, 30] (the removed elements)
console.log(numbers); // [10, 25, 35, 40, 50] (the modified original array)
```

**Exercise 28.2:** Use `splice()` to insert elements into the middle of an array without removing any elements.

**Expected Answer:**
```javascript
const letters = ["a", "b", "e", "f"];
letters.splice(2, 0, "c", "d");
console.log(letters); // ["a", "b", "c", "d", "e", "f"]
// By using 0 as the deleteCount, no elements are removed
```

**Exercise 28.3:** Use `splice()` to remove the last 3 elements from an array.

**Expected Answer:**
```javascript
const numbers = [10, 20, 30, 40, 50, 60];
const removed = numbers.splice(-3);
console.log(removed); // [40, 50, 60]
console.log(numbers); // [10, 20, 30]
```

**Exercise 28.4:** Compare `splice()` and `slice()` methods. How are they different?

**Expected Answer:**
```javascript
const original = [1, 2, 3, 4, 5];

// slice() creates a new array, doesn't modify the original
const sliced = original.slice(1, 3);
console.log(sliced);   // [2, 3]
console.log(original); // [1, 2, 3, 4, 5] (unchanged)

// splice() modifies the original array in place
const spliced = original.splice(1, 2);
console.log(spliced);  // [2, 3] (removed elements)
console.log(original); // [1, 4, 5] (modified)

/* Key differences:
   1. slice() doesn't modify the original array, splice() does
   2. slice() returns the selected elements, splice() returns the removed elements
   3. splice() can remove, replace, and insert elements, slice() can only extract
   4. splice() uses (start, deleteCount, ...items), slice() uses (start, end)
*/
```

## 29. **sort() Method**

**Exercise 29.1:** Sort the array `[3, 1, 4, 1, 5, 9, 2, 6]` in ascending order.

**Expected Answer:**
```javascript
const numbers = [3, 1, 4, 1, 5, 9, 2, 6];
numbers.sort((a, b) => a - b);
console.log(numbers); // [1, 1, 2, 3, 4, 5, 6, 9]
```

**Exercise 29.2:** What happens when you call `sort()` with no arguments? Demonstrate with various data types.

**Expected Answer:**
```javascript
// Sorting numbers without a compare function
const numbers = [10, 2, 30, 5];
numbers.sort();
console.log(numbers); // [10, 2, 30, 5] -> Incorrect! Becomes [10, 2, 30, 5]

// This happens because sort() converts elements to strings by default
// and sorts them lexicographically:
console.log("10".localeCompare("2")); // -1 ('1' comes before '2' in lexicographic order)

// Sorting strings (works correctly)
const fruits = ["banana", "apple", "cherry", "date"];
fruits.sort();
console.log(fruits); // ["apple", "banana", "cherry", "date"]

// For mixed types, sort() converts everything to strings
const mixed = [42, "apple", true, null];
mixed.sort();
console.log(mixed); // [42, "apple", null, true]
// Converted to strings: "42", "apple", "null", "true" and sorted
```

**Exercise 29.3:** Sort an array of objects by a specific property.

**Expected Answer:**
```javascript
const people = [
  { name: "Charlie", age: 40 },
  { name: "Alice", age: 25 },
  { name: "Bob", age: 30 }
];

// Sort by name (ascending)
people.sort((a, b) => a.name.localeCompare(b.name));
console.log(people);
// [
//   { name: "Alice", age: 25 },
//   { name: "Bob", age: 30 },
//   { name: "Charlie", age: 40 }
// ]

// Sort by age (descending)
people.sort((a, b) => b.age - a.age);
console.log(people);
// [
//   { name: "Charlie", age: 40 },
//   { name: "Bob", age: 30 },
//   { name: "Alice", age: 25 }
// ]
```

**Exercise 29.4:** Create a function to sort an array of strings ignoring case.

**Expected Answer:**
```javascript
function sortIgnoringCase(arr) {
  return [...arr].sort((a, b) => a.toLowerCase().localeCompare(b.toLowerCase()));
}

const mixed = ["Apple", "banana", "Cherry", "date"];
const sorted = sortIgnoringCase(mixed);
console.log(sorted); // ["Apple", "banana", "Cherry", "date"]
```

**Exercise 29.5:** Does `sort()` create a new array? Demonstrate.

**Expected Answer:**
```javascript
const original = [3, 1, 4, 2];
const result = original.sort();

console.log(original); // [1, 2, 3, 4]
console.log(result);   // [1, 2, 3, 4]
console.log(original === result); // true

// sort() modifies the original array in place and returns the same array

// To avoid modifying the original, create a copy first:
const numbers = [3, 1, 4, 2];
const sortedCopy = [...numbers].sort();

console.log(numbers);    // [3, 1, 4, 2] (unchanged)
console.log(sortedCopy); // [1, 2, 3, 4]
```

## 30. **join() Method**

**Exercise 30.1:** Join the elements of the array `["Hello", "world", "of", "JavaScript"]` into a string with spaces between words.

**Expected Answer:**
```javascript
const words = ["Hello", "world", "of", "JavaScript"];
const sentence = words.join(" ");
console.log(sentence); // "Hello world of JavaScript"
```

**Exercise 30.2:** What happens when you call `join()` with no arguments? What's the default separator?

**Expected Answer:**
```javascript
const fruits = ["apple", "banana", "cherry"];
const defaultJoin = fruits.join();
console.log(defaultJoin); // "apple,banana,cherry"
// The default separator is a comma (",")
```

**Exercise 30.3:** Create a function that builds an HTML list from an array using `join()`.

**Expected Answer:**
```javascript
function createHtmlList(items, ordered = false) {
  const tag = ordered ? "ol" : "ul";
  const listItems = items.map(item => `  <li>${item}</li>`);
  return `<${tag}>\n${listItems.join("\n")}\n</${tag}>`;
}

const shoppingList = ["Milk", "Eggs", "Bread", "Cheese"];
console.log(createHtmlList(shoppingList));
/* Output:
<ul>
  <li>Milk</li>
  <li>Eggs</li>
  <li>Bread</li>
  <li>Cheese</li>
</ul>
*/

console.log(createHtmlList(["First", "Second", "Third"], true));
/* Output:
<ol>
  <li>First</li>
  <li>Second</li>
  <li>Third</li>
</ol>
*/
```

**Exercise 30.4:** Implement a simple CSV generator using `join()` for an array of arrays.

**Expected Answer:**
```javascript
function generateCSV(data) {
  // Convert each row to a comma-separated string
  const rows = data.map(row => row.join(","));
  
  // Join rows with newlines
  return rows.join("\n");
}

const data = [
  ["Name", "Age", "City"],
  ["Alice", "25", "New York"],
  ["Bob", "30", "San Francisco"],
  ["Charlie", "35", "Chicago"]
];

const csv = generateCSV(data);
console.log(csv);
/* Output:
Name,Age,City
Alice,25,New York
Bob,30,San Francisco
Charlie,35,Chicago
*/
```
