# JavaScript Hands-On Exercises (Week 5) - Objects

## Basic Object Operations

### Creating Objects

**Exercise 1: Object Literal Syntax**  
Create an object `person` with properties `name`, `age`, and `city`.

```javascript
let person = { name: "Alice", age: 25, city: "New York" };
console.log(person);
```

**Exercise 2: Using `new Object()`**  
Create an object using the `new Object()` syntax with properties for a car.

```javascript
let car = new Object();
car.brand = "Toyota";
car.model = "Corolla";
car.year = 2020;
console.log(car);
```

**Expected output:**
```
{ brand: 'Toyota', model: 'Corolla', year: 2020 }
```

**Exercise 3: Using `Object.create()`**  
Create an object `student` with `Object.create()`.

```javascript
let student = Object.create(null);
student.name = "John";
student.grade = "A";
student.id = 12345;
console.log(student);
```

**Exercise 4: Using a Factory Function**  
Create a factory function that returns a new object.

```javascript
function createPerson(name, age, city) {
    return {
        name: name,
        age: age,
        city: city
    };
}

let person1 = createPerson("Emma", 28, "Chicago");
let person2 = createPerson("James", 32, "Boston");
console.log(person1);
console.log(person2);
```

**Expected output:**
```
{ name: 'Emma', age: 28, city: 'Chicago' }
{ name: 'James', age: 32, city: 'Boston' }
```

### Accessing Properties

**Exercise 5: Dot Notation**  
Print the `name` property of the `person` object using dot notation.

```javascript
let person = { name: "Alice", age: 25, city: "New York" };
console.log(person.name);  // Alice
```

**Exercise 6: Bracket Notation**  
Print the `city` property of the `person` object using bracket notation.

```javascript
console.log(person["city"]);  // New York
```

**Exercise 7: Dynamic Property Access**  
Write a function that accesses a property dynamically based on a parameter.

```javascript
function getProperty(obj, propName) {
    return obj[propName];
}

console.log(getProperty(person, "age"));  // 25
console.log(getProperty(person, "name"));  // Alice
```

### Modifying Objects

**Exercise 8: Change a Property Value**  
Change the `city` property of `person` to `"Los Angeles"`.

```javascript
person.city = "Los Angeles";
console.log(person.city);  // Los Angeles
```

**Exercise 9: Add a New Property**  
Add a `job` property to `person` with the value `"Engineer"`.

```javascript
person.job = "Engineer";
console.log(person);
```

**Expected output:**
```
{ name: 'Alice', age: 25, city: 'Los Angeles', job: 'Engineer' }
```

**Exercise 10: Delete a Property**  
Remove the `age` property from `person`.

```javascript
delete person.age;
console.log(person);
```

**Expected output:**
```
{ name: 'Alice', city: 'Los Angeles', job: 'Engineer' }
```

### Checking Properties

**Exercise 11: Check if Property Exists**  
Check if `age` exists in `person` using the `in` operator.

```javascript
console.log("age" in person);  // false (after deletion)
console.log("name" in person);  // true
```

**Exercise 12: Using `hasOwnProperty()`**  
Check if `name` is an own property of `person`.

```javascript
console.log(person.hasOwnProperty("name"));  // true
console.log(person.hasOwnProperty("toString"));  // false
```

**Exercise 13: Differentiating Own vs. Inherited Properties**  
Create an object and check both own and inherited properties.

```javascript
let vehicle = { type: "car" };
let toyota = Object.create(vehicle);
toyota.brand = "Toyota";

console.log(toyota.hasOwnProperty("brand"));  // true (own property)
console.log(toyota.hasOwnProperty("type"));   // false (inherited property)
console.log("type" in toyota);               // true (exists in prototype chain)
```

### Iterating Through Objects

**Exercise 14: Using `for...in` Loop**  
Loop through all properties of `person`.

```javascript
let person = { name: "Alice", city: "Los Angeles", job: "Engineer" };

for (let key in person) {
    console.log(`${key}: ${person[key]}`);
}
```

**Expected output:**
```
name: Alice
city: Los Angeles
job: Engineer
```

**Exercise 15: `Object.keys()`**  
Get all keys of an object as an array.

```javascript
let keys = Object.keys(person);
console.log(keys);  // ['name', 'city', 'job']

// Iterate through the keys
keys.forEach(key => {
    console.log(`Key: ${key}, Value: ${person[key]}`);
});
```

**Exercise 16: `Object.values()`**  
Get all values of an object as an array.

```javascript
let values = Object.values(person);
console.log(values);  // ['Alice', 'Los Angeles', 'Engineer']
```

**Exercise 17: `Object.entries()`**  
Convert an object to an array of key-value pairs and iterate through them.

```javascript
let entries = Object.entries(person);
console.log(entries);  
// [['name', 'Alice'], ['city', 'Los Angeles'], ['job', 'Engineer']]

entries.forEach(([key, value]) => {
    console.log(`${key} => ${value}`);
});
```

**Expected output:**
```
name => Alice
city => Los Angeles
job => Engineer
```

## Advanced Object Operations

### Methods in Objects

**Exercise 18: Create a Method Inside an Object**  
Add a method `greet` to `person`.

```javascript
person.greet = function() {
    return `Hello, my name is ${this.name}`;
};
console.log(person.greet());  // Hello, my name is Alice
```

**Exercise 19: Using `this` in Methods**  
Create an object with multiple methods that use `this`.

```javascript
let calculator = {
    value: 0,
    add(n) {
        this.value += n;
        return this;
    },
    subtract(n) {
        this.value -= n;
        return this;
    },
    getValue() {
        return this.value;
    }
};

console.log(calculator.add(5).subtract(2).getValue());  // 3
```

**Exercise 20: Method Shorthand Notation**  
Rewrite the calculator object using method shorthand syntax.

```javascript
let calculator = {
    value: 0,
    add(n) {
        this.value += n;
        return this;
    },
    subtract(n) {
        this.value -= n;
        return this;
    },
    getValue() {
        return this.value;
    }
};
```

### Object Copying and Merging

**Exercise 21: Shallow Copy with Object References**  
What happens when you copy an object by reference?

```javascript
let obj1 = { name: "Alice" };
let obj2 = obj1;
obj2.name = "Bob";

console.log(obj1.name);  // Bob (both variables reference the same object)
```

**Exercise 22: Shallow Copy with `Object.assign()`**  
Create a shallow copy of an object.

```javascript
let original = { a: 1, b: 2 };
let copy = Object.assign({}, original);
copy.a = 100;

console.log(original.a);  // 1
console.log(copy.a);      // 100
```

**Exercise 23: Nested Object Copy Problem**  
What happens with nested objects when using shallow copy?

```javascript
let original = { 
    name: "Alice", 
    address: { city: "New York", zip: "10001" } 
};
let copy = Object.assign({}, original);

copy.address.city = "Boston";
console.log(original.address.city);  // Boston (nested objects are still referenced)
```

**Exercise 24: Deep Copy with JSON**  
Create a deep copy of an object with nested structures.

```javascript
let original = { 
    name: "Alice", 
    address: { city: "New York", zip: "10001" } 
};

let deepCopy = JSON.parse(JSON.stringify(original));
deepCopy.address.city = "Boston";

console.log(original.address.city);  // New York
console.log(deepCopy.address.city);  // Boston
```

**Exercise 25: Merge Objects with `Object.assign()`**  
Merge two objects.

```javascript
let objA = { a: 1, b: 2 };
let objB = { b: 3, c: 4 };  // Note overlapping property 'b'

let merged = Object.assign({}, objA, objB);
console.log(merged);  // { a: 1, b: 3, c: 4 }
```

**Exercise 26: Spread Operator for Merging**  
Merge objects using the spread operator.

```javascript
let objA = { a: 1, b: 2 };
let objB = { b: 3, c: 4 };

let merged = { ...objA, ...objB };
console.log(merged);  // { a: 1, b: 3, c: 4 }
```

### Object Property Features

**Exercise 27: Property Shorthand**  
Use shorthand property names.

```javascript
let name = "Alice";
let age = 25;

// Instead of { name: name, age: age }
let person = { name, age };
console.log(person);  // { name: 'Alice', age: 25 }
```

**Exercise 28: Computed Property Names**  
Use a computed property name.

```javascript
let propName = "score";
let game = { [propName]: 100 };
console.log(game.score);  // 100

// More complex computed properties
function generateKey(prefix, id) {
    return `${prefix}_${id}`;
}

let obj = {
    [generateKey("user", 123)]: "value"
};
console.log(obj.user_123);  // value
```

**Exercise 29: Getters and Setters**  
Define getters and setters for controlled property access.

```javascript
let person = {
    _name: "Alice",  // Convention for "private" property
    
    get name() {
        return this._name;
    },
    
    set name(newName) {
        if (newName.length < 2) {
            console.log("Name is too short");
            return;
        }
        this._name = newName;
    }
};

console.log(person.name);  // Alice
person.name = "B";         // Name is too short
console.log(person.name);  // Alice
person.name = "Bob";
console.log(person.name);  // Bob
```

**Exercise 30: Property Descriptors**  
Use `Object.defineProperty()` to create a non-enumerable property.

```javascript
let user = { name: "Alice" };

Object.defineProperty(user, "id", {
    value: 12345,
    enumerable: false,  // Won't show up in for...in or Object.keys()
    writable: false     // Can't be changed
});

console.log(user.id);  // 12345
user.id = 9999;        // Won't change (in strict mode, would throw error)
console.log(user.id);  // 12345

// Property won't appear in enumeration
console.log(Object.keys(user));  // ['name']
```

### Object Immutability

**Exercise 31: `Object.freeze()`**  
Make an object immutable.

```javascript
let config = { 
    apiKey: "12345",
    server: "api.example.com" 
};

Object.freeze(config);
config.apiKey = "67890";  // This won't change
config.newProp = "test";  // This won't be added

console.log(config.apiKey);    // 12345
console.log(config.newProp);   // undefined
console.log(Object.isFrozen(config));  // true
```

**Exercise 32: `Object.seal()`**  
Prevent adding or removing properties, but allow changing existing ones.

```javascript
let user = { name: "Alice" };

Object.seal(user);
user.name = "Bob";       // This works
user.age = 25;           // This won't be added

console.log(user.name);  // Bob
console.log(user.age);   // undefined
console.log(Object.isSealed(user));  // true
```

## Object-Oriented Programming

### Constructor Functions

**Exercise 33: Basic Constructor Function**  
Create a `Person` constructor function.

```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
    
    this.greet = function() {
        return `Hello, my name is ${this.name}`;
    };
}

let person1 = new Person("Alice", 25);
let person2 = new Person("Bob", 30);

console.log(person1.name);      // Alice
console.log(person2.age);       // 30
console.log(person1.greet());   // Hello, my name is Alice
```

**Exercise 34: Forgetting `new` with Constructors**  
What happens if you forget `new` when calling a constructor function?

```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}

// let person = Person("Charlie", 35);  // Without new
// console.log(person);  // undefined
// console.log(window.name);  // In a browser, would be "Charlie"

// Safeguard against missing new
function SafePerson(name, age) {
    if (!(this instanceof SafePerson)) {
        return new SafePerson(name, age);
    }
    this.name = name;
    this.age = age;
}

let p1 = SafePerson("Charlie", 35);  // Still works
console.log(p1.name);  // Charlie
```

### Prototypes

**Exercise 35: Add Method to Prototype**  
Add a method to `Person.prototype`.

```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}

// Add method to prototype instead of constructor
Person.prototype.greet = function() {
    return `Hi, I am ${this.name}`;
};

let p1 = new Person("Alice", 25);
let p2 = new Person("Bob", 30);

console.log(p1.greet());  // Hi, I am Alice
console.log(p2.greet());  // Hi, I am Bob

// Shows that objects share the same method
console.log(p1.greet === p2.greet);  // true
```

**Exercise 36: Finding an Object's Prototype**  
Find the prototype of an object.

```javascript
function Person(name) {
    this.name = name;
}

let p1 = new Person("Alice");

console.log(Object.getPrototypeOf(p1) === Person.prototype);  // true
console.log(p1.__proto__ === Person.prototype);  // true (non-standard but widely supported)
```

**Exercise 37: Prototype Chain**  
Explore the prototype chain.

```javascript
function Person(name) {
    this.name = name;
}

Person.prototype.greet = function() {
    return `Hello, ${this.name}`;
};

let p1 = new Person("Alice");

console.log(p1.hasOwnProperty("name"));          // true - own property
console.log(p1.hasOwnProperty("greet"));         // false - from prototype
console.log("greet" in p1);                      // true - available in chain
console.log(p1.toString === Object.prototype.toString);  // true - from Object.prototype
```

**Exercise 38: Object.create() for Inheritance**  
Create an object that inherits from another object.

```javascript
let animal = {
    makeSound() {
        return "Some generic sound";
    }
};

let dog = Object.create(animal);
dog.makeSound = function() {
    return "Woof!";
};

let cat = Object.create(animal);
cat.makeSound = function() {
    return "Meow!";
};

console.log(dog.makeSound());  // Woof!
console.log(cat.makeSound());  // Meow!

let fish = Object.create(animal);
console.log(fish.makeSound());  // Some generic sound (inherited)
```

### Serialization

**Exercise 39: Converting Object to JSON**  
Serialize an object.

```javascript
let person = { 
    name: "Alice", 
    age: 25,
    city: "New York",
    greet() {
        return `Hello, I'm ${this.name}`;
    }
};

let jsonString = JSON.stringify(person);
console.log(jsonString);
// {"name":"Alice","age":25,"city":"New York"}
// Note: methods are excluded
```

**Exercise 40: Custom JSON Serialization**  
Control JSON serialization with `toJSON` method.

```javascript
let person = { 
    name: "Alice", 
    password: "secret123",
    birthDate: new Date(1995, 11, 17),
    
    toJSON() {
        // Custom representation without password
        return {
            name: this.name,
            birthYear: this.birthDate.getFullYear()
        };
    }
};

console.log(JSON.stringify(person));
// {"name":"Alice","birthYear":1995}
```

**Exercise 41: Parse JSON to Object**  
Convert JSON back to an object.

```javascript
let jsonString = '{"name":"Alice","age":25,"city":"New York"}';
let parsedObject = JSON.parse(jsonString);

console.log(parsedObject.name);  // Alice
console.log(parsedObject.age);   // 25
```

**Exercise 42: Custom JSON Parsing**  
Control JSON parsing with a reviver function.

```javascript
let jsonString = '{"name":"Alice","birthDate":"1995-12-17T00:00:00.000Z"}';

let parsedWithReviver = JSON.parse(jsonString, function(key, value) {
    if (key === "birthDate") {
        return new Date(value);
    }
    return value;
});

console.log(parsedWithReviver.birthDate instanceof Date);  // true
console.log(parsedWithReviver.birthDate.getFullYear());   // 1995
```

### Object Method Overrides

**Exercise 43: Override `toString()` Method**  
Override the `toString()` method.

```javascript
let book = {
    title: "JavaScript Guide",
    author: "Jane Doe",
    toString() {
        return `Book: ${this.title} by ${this.author}`;
    }
};

console.log(book.toString());  // Book: JavaScript Guide by Jane Doe
console.log("" + book);        // Book: JavaScript Guide by Jane Doe
```

**Exercise 44: Override `valueOf()` Method**  
Override `valueOf()` to return a number.

```javascript
let counter = {
    count: 0,
    increment() {
        this.count++;
        return this;
    },
    valueOf() {
        return this.count;
    }
};

counter.increment().increment().increment();
console.log(counter + 1);  // 4 (3 + 1)
```

## Practical Exercises

**Exercise 45: Create a Simple Object-Based Shopping Cart**  
Implement a shopping cart using objects.

```javascript
let shoppingCart = {
    items: [],
    
    addItem(name, price, quantity = 1) {
        this.items.push({
            name: name,
            price: price,
            quantity: quantity
        });
    },
    
    removeItem(name) {
        this.items = this.items.filter(item => item.name !== name);
    },
    
    getTotal() {
        return this.items.reduce((total, item) => {
            return total + (item.price * item.quantity);
        }, 0);
    },
    
    getItemCount() {
        return this.items.reduce((count, item) => count + item.quantity, 0);
    },
    
    clear() {
        this.items = [];
    },
    
    getCartInfo() {
        return {
            itemCount: this.getItemCount(),
            total: this.getTotal(),
            items: [...this.items]  // Return a copy
        };
    }
};

shoppingCart.addItem("Laptop", 999.99);
shoppingCart.addItem("Headphones", 79.99, 2);
console.log(shoppingCart.getCartInfo());
// { itemCount: 3, total: 1159.97, items: [...] }

shoppingCart.removeItem("Laptop");
console.log(shoppingCart.getCartInfo());
// { itemCount: 2, total: 159.98, items: [...] }
```

**Exercise 46: Design a Student Management System**  
Create a system to manage students and courses.

```javascript
// Constructor functions
function Student(id, name) {
    this.id = id;
    this.name = name;
    this.courses = [];
}

Student.prototype.enroll = function(course) {
    if (!this.courses.includes(course)) {
        this.courses.push(course);
        course.addStudent(this);
    }
};

Student.prototype.getCourses = function() {
    return this.courses.map(course => course.name);
};

function Course(id, name, maxStudents) {
    this.id = id;
    this.name = name;
    this.maxStudents = maxStudents;
    this.students = [];
}

Course.prototype.addStudent = function(student) {
    if (this.students.length < this.maxStudents && 
        !this.students.includes(student)) {
        this.students.push(student);
    } else if (this.students.length >= this.maxStudents) {
        console.log(`Course ${this.name} is full`);
    }
};

Course.prototype.getStudents = function() {
    return this.students.map(student => student.name);
};

// Usage
let john = new Student(1, "John");
let alice = new Student(2, "Alice");

let mathCourse = new Course(101, "Mathematics", 2);
let csCourse = new Course(102, "Computer Science", 1);

john.enroll(mathCourse);
alice.enroll(mathCourse);
alice.enroll(csCourse);

console.log(john.getCourses());  // ["Mathematics"]
console.log(alice.getCourses()); // ["Mathematics", "Computer Science"]
console.log(mathCourse.getStudents()); // ["John", "Alice"]
```




