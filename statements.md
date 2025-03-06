# JavaScript Hands-On Exercises 

## Basic JavaScript Concepts

### Statements and Expressions

**Exercise 1:**  
What will be logged in the following code?

```javascript
console.log(2 + 2 * 3);
```

**Answer:**  
`8` (Multiplication happens before addition due to operator precedence)

**Exercise 2:**  
What is the result of the following expression?

```javascript
console.log(5 * (2 + 3) - 4);
```

**Answer:**  
`21` (Parentheses are evaluated first, so 5 * 5 = 25, then 25 - 4 = 21)

**Exercise 3:**  
What is the value of `result` after this code executes?

```javascript
let x = 10;
let y = 5;
let result = x++ - --y;
```

**Answer:**  
`6` (x++ uses the current value of x (10) then increments it, --y decrements y first to 4, so 10 - 4 = 6)

### Empty Statement

**Exercise 4:**  
What will be logged in the following code?

```javascript
if (true) ; 
console.log("Hello");
```

**Answer:**  
`"Hello"` (The semicolon acts as an empty statement, so the `if` condition does nothing, and `"Hello"` is always printed regardless of the condition)

**Exercise 5:**  
What is the output of this code?

```javascript
for (let i = 0; i < 3; i++);
console.log(i);
```

**Answer:**  
`ReferenceError: i is not defined` (The semicolon creates an empty block, and `i` is only scoped within the for loop)

## Conditional Statements

### if Statement

**Exercise 6:**  
Write a program that prints `"Pass"` if `score` is 50 or above, otherwise `"Fail"`.

```javascript
let score = 60;
if (score >= 50) {
    console.log("Pass");
} else {
    console.log("Fail");
}
```

**Answer:**  
If `score = 60`, output is `"Pass"`

**Exercise 7:**  
What will this code output?

```javascript
let a = 0;
let b = "0";
if (a === b) {
    console.log("Equal");
} else {
    console.log("Not equal");
}
```

**Answer:**  
`"Not equal"` (=== checks both value and type, and these are different types)

### Ternary Operator

**Exercise 8:**  
Rewrite the following `if` statement using the ternary operator:

```javascript
let age = 18;
let status;

if (age >= 18) {
  status = "Adult";
} else {
  status = "Minor";
}
```

**Answer:**  
```javascript
let status = age >= 18 ? "Adult" : "Minor";
```

**Exercise 9:**  
Use nested ternary operators to assign a string based on a score:
- "Excellent" if score is 90 or above
- "Good" if score is between 70 and 89
- "Average" if score is between 50 and 69
- "Poor" if score is below 50

```javascript
let score = 85;
let grade = ?
```

**Answer:**  
```javascript
let grade = score >= 90 ? "Excellent" : 
            score >= 70 ? "Good" : 
            score >= 50 ? "Average" : "Poor";
```

### else if Ladder

**Exercise 10:**  
Write a program that checks a number and prints:
- `"Positive"` if it's greater than 0
- `"Negative"` if it's less than 0
- `"Zero"` otherwise

```javascript
let num = -5;

if (num > 0) {
    console.log("Positive");
} else if (num < 0) {
    console.log("Negative");
} else {
    console.log("Zero");
}
```

**Answer:**  
If `num = -5`, output is `"Negative"`

**Exercise 11:**  
Write code that assigns a letter grade based on a numerical score:
- "A" for 90-100
- "B" for 80-89
- "C" for 70-79
- "D" for 60-69
- "F" for below 60

```javascript
let score = 78;
let letterGrade;

// Your code here
```

**Answer:**  
```javascript
if (score >= 90) {
    letterGrade = "A";
} else if (score >= 80) {
    letterGrade = "B";
} else if (score >= 70) {
    letterGrade = "C";
} else if (score >= 60) {
    letterGrade = "D";
} else {
    letterGrade = "F";
}
```

### switch Statement

**Exercise 12:**  
Convert the following `if-else` into a `switch` statement:

```javascript
let fruit = "apple";

if (fruit === "apple") console.log("Red");
else if (fruit === "banana") console.log("Yellow");
else console.log("Unknown color");
```

**Answer:**  
```javascript
switch (fruit) {
    case "apple":
        console.log("Red");
        break;
    case "banana":
        console.log("Yellow");
        break;
    default:
        console.log("Unknown color");
}
```

**Exercise 13:**  
Write a `switch` statement that logs a message based on the day of the week (1-7):

```javascript
let day = 3;
// Your code here
```

**Answer:**  
```javascript
switch (day) {
    case 1:
        console.log("Monday");
        break;
    case 2:
        console.log("Tuesday");
        break;
    case 3:
        console.log("Wednesday");
        break;
    case 4:
        console.log("Thursday");
        break;
    case 5:
        console.log("Friday");
        break;
    case 6:
        console.log("Saturday");
        break;
    case 7:
        console.log("Sunday");
        break;
    default:
        console.log("Invalid day");
}
```

**Exercise 14:**  
What is the output of the following code? Fix any issues.

```javascript
let fruit = "apple";
switch (fruit) {
    case "banana":
        console.log("Yellow fruit");
    case "apple":
        console.log("Red fruit");
    case "kiwi":
        console.log("Green fruit");
    default:
        console.log("Unknown fruit");
}
```

**Answer:**  
Output: `"Red fruit"`, `"Green fruit"`, `"Unknown fruit"` (Fall-through behavior because `break` statements are missing)

Fixed code:
```javascript
let fruit = "apple";
switch (fruit) {
    case "banana":
        console.log("Yellow fruit");
        break;
    case "apple":
        console.log("Red fruit");
        break;
    case "kiwi":
        console.log("Green fruit");
        break;
    default:
        console.log("Unknown fruit");
}
```

## Loops

### while Loop

**Exercise 15:**  
Print numbers from 1 to 5 using a `while` loop.

```javascript
let i = 1;
while (i <= 5) {
    console.log(i);
    i++;
}
```

**Answer:**  
Output: 
```
1
2
3
4
5
```

**Exercise 16:**  
Write a `while` loop that calculates the sum of numbers from 1 to 10.

```javascript
// Your code here
```

**Answer:**  
```javascript
let sum = 0;
let num = 1;

while (num <= 10) {
    sum += num;
    num++;
}

console.log(sum); // 55
```

### do...while Loop

**Exercise 17:**  
Modify Exercise 15 to use a `do...while` loop.

```javascript
let i = 1;
do {
    console.log(i);
    i++;
} while (i <= 5);
```

**Answer:**  
Output is the same as Exercise 15

**Exercise 18:**  
What's the difference between `while` and `do...while`? Demonstrate with an example where they behave differently.

**Answer:**  
The key difference is that a `do...while` loop always executes at least once, while a `while` loop might not execute at all.

Example:
```javascript
let x = 10;

// while loop
while (x < 10) {
    console.log("while: " + x);
    x++;
}

// do...while loop
do {
    console.log("do...while: " + x);
    x++;
} while (x < 10);
```

Output:
```
do...while: 10
```
(Only the do...while loop runs once, the while loop doesn't run at all)

### for Loop

**Exercise 19:**  
Print numbers from 1 to 5 using a `for` loop.

```javascript
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

**Answer:**  
Output: 
```
1
2
3
4
5
```

**Exercise 20:**  
Write a `for` loop that prints all even numbers from 2 to 10.

```javascript
// Your code here
```

**Answer:**  
```javascript
for (let i = 2; i <= 10; i += 2) {
    console.log(i);
}
```

Output:
```
2
4
6
8
10
```

**Exercise 21:**  
What happens in the following code?

```javascript
for (;;) {
    console.log("Hello");
}
```

**Answer:**  
It creates an infinite loop because no condition stops the loop.

### for...of Loop (Arrays)

**Exercise 22:**  
Print all elements of an array using `for...of`.

```javascript
let colors = ["red", "blue", "green"];
for (let color of colors) {
    console.log(color);
}
```

**Answer:**  
Output:
```
red
blue
green
```

**Exercise 23:**  
Calculate the sum of all numbers in an array using `for...of`.

```javascript
let numbers = [10, 20, 30, 40, 50];
// Your code here
```

**Answer:**  
```javascript
let numbers = [10, 20, 30, 40, 50];
let sum = 0;

for (let num of numbers) {
    sum += num;
}

console.log(sum); // 150
```

### for...in Loop (Objects)

**Exercise 24:**  
Print all keys and values of an object.

```javascript
let person = { name: "Alice", age: 25, city: "New York" };

for (let key in person) {
    console.log(key + ": " + person[key]);
}
```

**Answer:**  
Output:
```
name: Alice
age: 25
city: New York
```

**Exercise 25:**  
What happens if you use `for...in` with an array? Is it recommended?

```javascript
let colors = ["red", "blue", "green"];

for (let i in colors) {
    console.log(i, colors[i]);
}
```

**Answer:**  
Output:
```
0 red
1 blue
2 green
```

It prints the indices (as strings) and values. It's not recommended for arrays because it also iterates over non-element properties that may have been added to the array, and doesn't guarantee order.

## Jump Statements

### break Statement

**Exercise 26:**  
Stop a loop when `i` reaches 3.

```javascript
for (let i = 1; i <= 5; i++) {
    if (i === 3) break;
    console.log(i);
}
```

**Answer:**  
Output:
```
1
2
```

**Exercise 27:**  
Write a program that searches for a number in an array and prints its position. Use `break` when found.

```javascript
let numbers = [10, 20, 30, 40, 50];
let searchFor = 30;
// Your code here
```

**Answer:**  
```javascript
let found = false;
let position = -1;

for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] === searchFor) {
        found = true;
        position = i;
        break;
    }
}

if (found) {
    console.log(`Number ${searchFor} found at position ${position}`);
} else {
    console.log(`Number ${searchFor} not found`);
}
```

### continue Statement

**Exercise 28:**  
Skip printing the number 3.

```javascript
for (let i = 1; i <= 5; i++) {
    if (i === 3) continue;
    console.log(i);
}
```

**Answer:**  
Output:
```
1
2
4
5
```

**Exercise 29:**  
Write a loop that prints only even numbers from 1 to 10 using `continue`.

```javascript
// Your code here
```

**Answer:**  
```javascript
for (let i = 1; i <= 10; i++) {
    if (i % 2 !== 0) continue;
    console.log(i);
}
```

Output:
```
2
4
6
8
10
```

### Labeled Statements

**Exercise 30:**  
What is the output of the following?

```javascript
outer: for (let i = 0; i < 3; i++) {
    for (let j = 0; j < 3; j++) {
        if (j === 1) break outer;
        console.log(i, j);
    }
}
```

**Answer:**  
Only `0 0` is printed because `break outer;` exits both loops.

**Exercise 31:**  
Use a labeled continue statement to skip the current iteration of an outer loop.

```javascript
// Your code here
```

**Answer:**  
```javascript
outerLoop: for (let i = 0; i < 3; i++) {
    for (let j = 0; j < 3; j++) {
        if (i === 1 && j === 1) {
            console.log(`Skipping outer loop when i=${i}`);
            continue outerLoop;
        }
        console.log(i, j);
    }
}
```

Output:
```
0 0
0 1
0 2
1 0
Skipping outer loop when i=1
2 0
2 1
2 2
```

## Functions and Error Handling

### return in Functions

**Exercise 32:**  
Write a function that returns the sum of two numbers.

```javascript
function sum(a, b) {
    return a + b;
}
console.log(sum(5, 3)); // 8
```

**Exercise 33:**  
Write a function that returns the larger of two numbers.

```javascript
// Your code here
```

**Answer:**  
```javascript
function max(a, b) {
    return a > b ? a : b;
}

console.log(max(10, 5)); // 10
console.log(max(3, 7));  // 7
```

### throw Statement

**Exercise 34:**  
Throw an error if `age` is less than 18.

```javascript
function checkAge(age) {
    if (age < 18) throw new Error("Too young!");
    return "Access granted";
}

console.log(checkAge(20)); // Access granted
// console.log(checkAge(16)); // Error: Too young!
```

**Exercise 35:**  
Write a function that divides two numbers but throws an error if the divisor is zero.

```javascript
// Your code here
```

**Answer:**  
```javascript
function divide(a, b) {
    if (b === 0) {
        throw new Error("Division by zero is not allowed");
    }
    return a / b;
}

console.log(divide(10, 2)); // 5
// console.log(divide(10, 0)); // Error: Division by zero is not allowed
```

### try...catch

**Exercise 36:**  
Handle the error from Exercise 34.

```javascript
try {
    console.log(checkAge(16));
} catch (error) {
    console.log("Error:", error.message);
}
```

**Answer:**  
Output: `Error: Too young!`

**Exercise 37:**  
Write a function that converts a string to an integer and handles invalid inputs with try...catch.

```javascript
// Your code here
```

**Answer:**  
```javascript
function convertToInteger(str) {
    try {
        const num = parseInt(str, 10);
        if (isNaN(num)) {
            throw new Error("Invalid number format");
        }
        return num;
    } catch (error) {
        return "Conversion error: " + error.message;
    }
}

console.log(convertToInteger("123")); // 123
console.log(convertToInteger("abc")); // Conversion error: Invalid number format
```

### debugger Statement

**Exercise 38:**  
Where does execution pause?

```javascript
function test() {
    let a = 5;
    debugger;
    let b = 10;
    console.log(a + b);
}
test();
```

**Answer:**  
Execution pauses at `debugger;` in the browser console.

**Exercise 39:**  
Use the debugger statement to help find the bug in this function.

```javascript
function calculateAverage(numbers) {
    let sum = 0;
    for (let i = 0; i <= numbers.length; i++) {
        debugger;
        sum += numbers[i];
    }
    return sum / numbers.length;
}

console.log(calculateAverage([1, 2, 3, 4]));
```

**Answer:**  
The bug is in the for loop condition: `i <= numbers.length` should be `i < numbers.length` to prevent accessing an undefined element.

## Advanced Practice

**Exercise 40:**  
Write a function that checks if a number is even.

```javascript
function isEven(number) {
    return number % 2 === 0;
}

console.log(isEven(4)); // true
console.log(isEven(7)); // false
```

**Exercise 41:**  
Implement a countdown from 10 to 1 using a `while` loop.

```javascript
let count = 10;
while (count >= 1) {
    console.log(count);
    count--;
}
```

**Exercise 42:**  
Use `switch` to handle multiple cases for days of the week.

```javascript
function getDayType(day) {
    day = day.toLowerCase();
    
    switch (day) {
        case "monday":
        case "tuesday":
        case "wednesday":
        case "thursday":
        case "friday":
            return "Weekday";
        case "saturday":
        case "sunday":
            return "Weekend";
        default:
            return "Invalid day";
    }
}

console.log(getDayType("Monday")); // Weekday
console.log(getDayType("Sunday")); // Weekend
console.log(getDayType("Funday")); // Invalid day
```

**Exercise 43:**  
Use `break` inside a `for` loop to exit when you find the first negative number in an array.

```javascript
function findFirstNegative(numbers) {
    let foundNegative = false;
    let negativeNumber = null;
    
    for (let i = 0; i < numbers.length; i++) {
        if (numbers[i] < 0) {
            foundNegative = true;
            negativeNumber = numbers[i];
            break;
        }
    }
    
    return foundNegative ? `Found negative number: ${negativeNumber}` : "No negative numbers found";
}

console.log(findFirstNegative([5, 10, -3, 7, -8])); // Found negative number: -3
console.log(findFirstNegative([5, 10, 15]));        // No negative numbers found
```

**Exercise 44:**  
Write a function that throws an error for invalid input.

```javascript
function calculateSquareRoot(number) {
    if (typeof number !== 'number') {
        throw new TypeError("Input must be a number");
    }
    
    if (number < 0) {
        throw new RangeError("Cannot calculate square root of negative number");
    }
    
    return Math.sqrt(number);
}

// calculateSquareRoot("4"); // TypeError: Input must be a number
// calculateSquareRoot(-9);  // RangeError: Cannot calculate square root of negative number
console.log(calculateSquareRoot(16)); // 4
```

**Exercise 45:**  
Use `try...catch` to handle exceptions gracefully.

```javascript
function safelyCalculateSquareRoot(input) {
    try {
        const result = calculateSquareRoot(input);
        return `The square root is ${result}`;
    } catch (error) {
        if (error instanceof TypeError) {
            return "Type error: Please provide a number";
        } else if (error instanceof RangeError) {
            return "Range error: Number must be non-negative";
        } else {
            return "An unknown error occurred: " + error.message;
        }
    }
}

console.log(safelyCalculateSquareRoot(16));  // The square root is 4
console.log(safelyCalculateSquareRoot("4")); // Type error: Please provide a number
console.log(safelyCalculateSquareRoot(-9));  // Range error: Number must be non-negative
```

**Exercise 46:**  
Use `debugger` to inspect a function that multiplies two numbers.

```javascript
function multiply(a, b) {
    debugger;
    let result = a * b;
    return result;
}

console.log(multiply(5, 3)); // 15
```

**Exercise 47:**  
Modify an array using `for...of`.

```javascript
function doubleAllNumbers(numbers) {
    let result = [];
    for (let num of numbers) {
        result.push(num * 2);
    }
    return result;
}

console.log(doubleAllNumbers([1, 2, 3, 4])); // [2, 4, 6, 8]
```

**Exercise 48:**  
Iterate over object properties using `for...in`.

```javascript
function copyAndModifyObject(obj) {
    let newObj = {};
    for (let key in obj) {
        if (typeof obj[key] === 'string') {
            newObj[key] = obj[key].toUpperCase();
        } else {
            newObj[key] = obj[key];
        }
    }
    return newObj;
}

console.log(copyAndModifyObject({name: "John", age: 30, city: "New York"}));
// {name: "JOHN", age: 30, city: "NEW YORK"}
```

**Exercise 49:**  
Convert a `while` loop into a `do...while`.

Original `while` loop:
```javascript
let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}
```

Converted to `do...while`:
```javascript
let i = 0;
do {
    console.log(i);
    i++;
} while (i < 5);
```

**Exercise 50:**  
Write a function that uses a nested loop to find pairs of numbers in an array that add up to a target sum.

```javascript
function findPairs(numbers, targetSum) {
    let pairs = [];
    
    for (let i = 0; i < numbers.length; i++) {
        for (let j = i + 1; j < numbers.length; j++) {
            if (numbers[i] + numbers[j] === targetSum) {
                pairs.push([numbers[i], numbers[j]]);
            }
        }
    }
    
    return pairs;
}

console.log(findPairs([1, 2, 3, 4, 5], 6)); // [[1, 5], [2, 4]]
```

---

## Bonus Challenge Exercises

**Exercise 51: FizzBuzz**  
Write a program that prints numbers from 1 to 100. For multiples of 3, print "Fizz" instead of the number. For multiples of 5, print "Buzz". For numbers that are multiples of both 3 and 5, print "FizzBuzz".

```javascript
for (let i = 1; i <= 100; i++) {
    if (i % 3 === 0 && i % 5 === 0) {
        console.log("FizzBuzz");
    } else if (i % 3 === 0) {
        console.log("Fizz");
    } else if (i % 5 === 0) {
        console.log("Buzz");
    } else {
        console.log(i);
    }
}
```

**Exercise 52: Prime Number Checker**  
Write a function that checks if a number is prime.

```javascript
function isPrime(num) {
    if (num <= 1) return false;
    if (num <= 3) return true;
    if (num % 2 === 0 || num % 3 === 0) return false;
    
    for (let i = 5; i * i <= num; i += 6) {
        if (num % i === 0 || num % (i + 2) === 0) return false;
    }
    
    return true;
}

console.log(isPrime(11)); // true
console.log(isPrime(15)); // false
```
