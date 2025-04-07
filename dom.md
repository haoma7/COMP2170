# 🧪 JavaScript DOM Manipulation: Beginner Practice Exercises

---

## 1. Select Element by ID and Change Text

**Question:**  
Given the following HTML:

```html
<p id="greeting">Hello!</p>
```

Write JavaScript to change the text to "Welcome to DOM Manipulation!"

<details>
<summary>💡 Click to reveal answer</summary>

```js
const greeting = document.getElementById("greeting");
greeting.textContent = "Welcome to DOM Manipulation!";
```

</details>

---

## 2. Change Element Style

**Question:**  
Given the HTML:

```html
<div id="box">This is a box</div>
```

Write JavaScript to change the background color of the box to light blue and add a border.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const box = document.getElementById("box");
box.style.backgroundColor = "lightblue";
box.style.border = "2px solid blue";
```

</details>

---

## 3. Select Elements by Class Name

**Question:**  
Given:

```html
<p class="highlight">First paragraph</p>
<p class="highlight">Second paragraph</p>
<p class="highlight">Third paragraph</p>
```

Write JavaScript to select all elements with class "highlight" and change their text color to red.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const highlightElements = document.getElementsByClassName("highlight");

for (let i = 0; i < highlightElements.length; i++) {
  highlightElements[i].style.color = "red";
}
```

</details>

---

## 4. Use querySelector to Select Elements

**Question:**  
Given:

```html
<ul id="fruits">
  <li>Apple</li>
  <li>Banana</li>
  <li>Orange</li>
</ul>
```

Use `querySelector` to select and make the first list item bold.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const firstFruit = document.querySelector("#fruits li");
firstFruit.style.fontWeight = "bold";
```

</details>

---

## 5. Use querySelectorAll for Multiple Elements

**Question:**  
Given:

```html
<div class="container">
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
  <p>Paragraph 3</p>
</div>
```

Use `querySelectorAll` to select all paragraphs inside the container and add a background color.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const paragraphs = document.querySelectorAll(".container p");

paragraphs.forEach(paragraph => {
  paragraph.style.backgroundColor = "lightyellow";
});
```

</details>

---

## 6. Create a New Element

**Question:**  
Given:

```html
<div id="container"></div>
```

Write JavaScript to create a new paragraph with the text "This paragraph was created with JavaScript" and add it to the container.

<details>
<summary>💡 Click to reveal answer</summary>

```js
// Create a new paragraph element
const newParagraph = document.createElement("p");

// Add text to the paragraph
newParagraph.textContent = "This paragraph was created with JavaScript";

// Append it to the container
document.getElementById("container").appendChild(newParagraph);
```

</details>

---

## 7. Add a Click Event Listener

**Question:**  
Given:

```html
<button id="clickMe">Click Me!</button>
<p id="output"></p>
```

Add a click event listener to the button that displays a message in the paragraph when clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("clickMe").addEventListener("click", function() {
  document.getElementById("output").textContent = "Button was clicked!";
});
```

</details>

---

## 8. Toggle Element Visibility

**Question:**  
Given:

```html
<button id="toggleBtn">Toggle</button>
<div id="content">This content can be hidden</div>
```

Write JavaScript to toggle the visibility of the content when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const toggleBtn = document.getElementById("toggleBtn");
const content = document.getElementById("content");

toggleBtn.addEventListener("click", function() {
  if (content.style.display === "none") {
    content.style.display = "block";
  } else {
    content.style.display = "none";
  }
});
```

</details>

---

## 9. Modify Element Attributes

**Question:**  
Given:

```html
<img id="myImage" src="image1.jpg" alt="Image 1">
<button id="changeImage">Change Image</button>
```

Write JavaScript to change the image source and alt text when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("changeImage").addEventListener("click", function() {
  const image = document.getElementById("myImage");
  image.src = "image2.jpg";
  image.alt = "Image 2";
});
```

</details>

---

## 10. Add and Remove Classes

**Question:**  
Given:

```html
<div id="highlight-box">This is a box</div>
<button id="addHighlight">Highlight</button>
<button id="removeHighlight">Remove Highlight</button>
```

Write JavaScript to add a class "highlighted" when the "Highlight" button is clicked and remove it when "Remove Highlight" is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const box = document.getElementById("highlight-box");
const addBtn = document.getElementById("addHighlight");
const removeBtn = document.getElementById("removeHighlight");

addBtn.addEventListener("click", function() {
  box.classList.add("highlighted");
});

removeBtn.addEventListener("click", function() {
  box.classList.remove("highlighted");
});
```

</details>

---

## 11. Toggle a Class

**Question:**  
Given:

```html
<div id="toggle-box">Click me to toggle</div>
```

Write JavaScript to toggle the class "active" on the div when it's clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const box = document.getElementById("toggle-box");

box.addEventListener("click", function() {
  this.classList.toggle("active");
});
```

</details>

---

## 12. Access Parent Elements

**Question:**  
Given:

```html
<div id="parent">
  <p id="child">This is a child paragraph</p>
</div>
```

Write JavaScript to select the paragraph and change the background color of its parent div.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const child = document.getElementById("child");
const parent = child.parentElement;
parent.style.backgroundColor = "lightgray";
```

</details>

---

## 13. Access Child Elements

**Question:**  
Given:

```html
<ul id="fruit-list">
  <li>Apple</li>
  <li>Banana</li>
  <li>Cherry</li>
</ul>
```

Write JavaScript to access the children of the list and make the second item text red.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const fruitList = document.getElementById("fruit-list");
const secondItem = fruitList.children[1];
secondItem.style.color = "red";
```

</details>

---

## 14. Remove Elements

**Question:**  
Given:

```html
<div id="container">
  <p id="para1">Paragraph 1</p>
  <p id="para2">Paragraph 2</p>
  <p id="para3">Paragraph 3</p>
</div>
<button id="removeBtn">Remove Paragraph 2</button>
```

Write JavaScript to remove the second paragraph when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("removeBtn").addEventListener("click", function() {
  const para2 = document.getElementById("para2");
  para2.remove();
});
```

</details>

---

## 15. Simple Form Validation

**Question:**  
Given:

```html
<form id="myForm">
  <input type="text" id="username" placeholder="Enter username">
  <p id="error" style="color: red; display: none;">Username cannot be empty</p>
  <button type="submit">Submit</button>
</form>
```

Write JavaScript to validate that the username is not empty when the form is submitted.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("myForm").addEventListener("submit", function(event) {
  const username = document.getElementById("username").value;
  const errorMsg = document.getElementById("error");
  
  if (username.trim() === "") {
    event.preventDefault(); // Prevent form submission
    errorMsg.style.display = "block";
  } else {
    errorMsg.style.display = "none";
  }
});
```

</details>

---

## 16. Create a Simple Counter

**Question:**  
Given:

```html
<div id="counter">0</div>
<button id="increment">+</button>
<button id="decrement">-</button>
```

Write JavaScript to create a counter that increments or decrements when the respective buttons are clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
let count = 0;
const counterDisplay = document.getElementById("counter");
const incrementBtn = document.getElementById("increment");
const decrementBtn = document.getElementById("decrement");

incrementBtn.addEventListener("click", function() {
  count++;
  counterDisplay.textContent = count;
});

decrementBtn.addEventListener("click", function() {
  count--;
  counterDisplay.textContent = count;
});
```

</details>

---

## 17. Change Text Input Value

**Question:**  
Given:

```html
<input type="text" id="myInput" value="Hello">
<button id="changeBtn">Change Text</button>
```

Write JavaScript to change the input value to "Hello World!" when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("changeBtn").addEventListener("click", function() {
  document.getElementById("myInput").value = "Hello World!";
});
```

</details>

---

## 18. Append Multiple Items to a List

**Question:**  
Given:

```html
<ul id="myList"></ul>
<button id="addItems">Add Items</button>
```

Write JavaScript to add three new list items (Item 1, Item 2, Item 3) when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("addItems").addEventListener("click", function() {
  const list = document.getElementById("myList");
  
  for (let i = 1; i <= 3; i++) {
    const item = document.createElement("li");
    item.textContent = `Item ${i}`;
    list.appendChild(item);
  }
});
```

</details>

---

## 19. Simple Show/Hide Functionality

**Question:**  
Given:

```html
<button id="showHideBtn">Show Content</button>
<div id="content" style="display: none;">
  <p>This is hidden content</p>
</div>
```

Write JavaScript to show or hide the content and update the button text accordingly.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("showHideBtn");
const content = document.getElementById("content");

button.addEventListener("click", function() {
  if (content.style.display === "none") {
    content.style.display = "block";
    button.textContent = "Hide Content";
  } else {
    content.style.display = "none";
    button.textContent = "Show Content";
  }
});
```

</details>

---

## 20. Handle Mouseover Event

**Question:**  
Given:

```html
<div id="hoverBox" style="width: 100px; height: 100px; background-color: lightblue;">
  Hover over me
</div>
```

Write JavaScript to change the background color when the mouse is over the div and change it back when the mouse leaves.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const box = document.getElementById("hoverBox");

box.addEventListener("mouseover", function() {
  this.style.backgroundColor = "lightgreen";
});

box.addEventListener("mouseout", function() {
  this.style.backgroundColor = "lightblue";
});
```

</details>

---

## 21. Add Elements to Specific Positions

**Question:**  
Given:

```html
<ul id="myList">
  <li>First Item</li>
  <li>Last Item</li>
</ul>
<button id="addMiddle">Add Middle Item</button>
```

Write JavaScript to add a new item between the first and last items when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("addMiddle").addEventListener("click", function() {
  const list = document.getElementById("myList");
  const newItem = document.createElement("li");
  newItem.textContent = "Middle Item";
  
  // Insert before the last item
  list.insertBefore(newItem, list.children[1]);
});
```

</details>

---

## 22. Get and Display Input Value

**Question:**  
Given:

```html
<input type="text" id="userInput" placeholder="Enter text">
<button id="showBtn">Show Text</button>
<p id="output"></p>
```

Write JavaScript to display the input value in the paragraph when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("showBtn").addEventListener("click", function() {
  const inputValue = document.getElementById("userInput").value;
  document.getElementById("output").textContent = inputValue;
});
```

</details>

---

## 23. Create a To-Do List Item

**Question:**  
Given:

```html
<input type="text" id="taskInput" placeholder="New task">
<button id="addTask">Add Task</button>
<ul id="taskList"></ul>
```

Write JavaScript to add a new task to the list when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("addTask").addEventListener("click", function() {
  const taskInput = document.getElementById("taskInput");
  const taskText = taskInput.value.trim();
  
  if (taskText !== "") {
    // Create new list item
    const newTask = document.createElement("li");
    newTask.textContent = taskText;
    
    // Add to list
    document.getElementById("taskList").appendChild(newTask);
    
    // Clear input
    taskInput.value = "";
  }
});
```

</details>

---

## 24. Create a Simple Dropdown Menu

**Question:**  
Given:

```html
<div class="dropdown">
  <button id="dropdownBtn">Menu</button>
  <div id="dropdownContent" style="display: none;">
    <a href="#">Link 1</a>
    <a href="#">Link 2</a>
    <a href="#">Link 3</a>
  </div>
</div>
```

Write JavaScript to show/hide the dropdown content when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const dropdownBtn = document.getElementById("dropdownBtn");
const dropdownContent = document.getElementById("dropdownContent");

dropdownBtn.addEventListener("click", function() {
  if (dropdownContent.style.display === "none") {
    dropdownContent.style.display = "block";
  } else {
    dropdownContent.style.display = "none";
  }
});
```

</details>

---

## 25. Use innerHTML to Add Content

**Question:**  
Given:

```html
<div id="container"></div>
<button id="addContent">Add Content</button>
```

Write JavaScript to add a heading and paragraph to the container when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("addContent").addEventListener("click", function() {
  const container = document.getElementById("container");
  container.innerHTML = `
    <h2>Welcome!</h2>
    <p>This content was added using innerHTML.</p>
  `;
});
```

</details>

---

## 26. Disable a Button

**Question:**  
Given:

```html
<button id="clickOnce">Click me once</button>
```

Write JavaScript to disable the button after it's clicked once.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("clickOnce");

button.addEventListener("click", function() {
  alert("Button was clicked!");
  this.disabled = true;
  this.textContent = "Button disabled";
});
```

</details>

---

## 27. Change Image Source on Click

**Question:**  
Given:

```html
<img id="toggleImage" src="image1.jpg" alt="Image 1">
<button id="changeImage">Switch Image</button>
```

Write JavaScript to toggle between two different images when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const image = document.getElementById("toggleImage");
const button = document.getElementById("changeImage");
let isFirstImage = true;

button.addEventListener("click", function() {
  if (isFirstImage) {
    image.src = "image2.jpg";
    image.alt = "Image 2";
    isFirstImage = false;
  } else {
    image.src = "image1.jpg";
    image.alt = "Image 1";
    isFirstImage = true;
  }
});
```

</details>

---

## 28. Simple Form Input Validation

**Question:**  
Given:

```html
<input type="text" id="numberInput" placeholder="Enter a number">
<button id="checkNumber">Check</button>
<p id="result"></p>
```

Write JavaScript to check if the input is a valid number and display a message accordingly.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("checkNumber").addEventListener("click", function() {
  const input = document.getElementById("numberInput").value;
  const result = document.getElementById("result");
  
  if (input === "") {
    result.textContent = "Please enter a value";
  } else if (isNaN(input)) {
    result.textContent = "This is not a number";
  } else {
    result.textContent = "Valid number!";
  }
});
```

</details>

---

## 29. Handle Keyboard Events

**Question:**  
Given:

```html
<input type="text" id="keyInput" placeholder="Type here">
<p id="keyOutput">Press a key</p>
```

Write JavaScript to display which key was pressed in the input field.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("keyInput").addEventListener("keydown", function(event) {
  document.getElementById("keyOutput").textContent = `You pressed: ${event.key}`;
});
```

</details>

---

## 30. Simple Accordion Effect

**Question:**  
Given:

```html
<div class="accordion">
  <div class="accordion-header">Click to expand</div>
  <div class="accordion-content" style="display: none;">
    <p>This is the hidden content that will be shown when clicked.</p>
  </div>
</div>
```

Write JavaScript to toggle the visibility of the content when the header is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const header = document.querySelector(".accordion-header");
const content = document.querySelector(".accordion-content");

header.addEventListener("click", function() {
  if (content.style.display === "none") {
    content.style.display = "block";
    header.textContent = "Click to collapse";
  } else {
    content.style.display = "none";
    header.textContent = "Click to expand";
  }
});
```

</details>

---

## 31. Find Element by Tag Name

**Question:**  
Given:

```html
<div id="container">
  <h1>Main Heading</h1>
  <p>First paragraph</p>
  <p>Second paragraph</p>
</div>
<button id="highlightParagraphs">Highlight Paragraphs</button>
```

Write JavaScript to find all paragraphs in the container and highlight them with a yellow background.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("highlightParagraphs").addEventListener("click", function() {
  const container = document.getElementById("container");
  const paragraphs = container.getElementsByTagName("p");
  
  for (let i = 0; i < paragraphs.length; i++) {
    paragraphs[i].style.backgroundColor = "yellow";
  }
});
```

</details>

---

## 32. Check/Uncheck All Checkboxes

**Question:**  
Given:

```html
<div>
  <input type="checkbox" id="selectAll">
  <label for="selectAll">Select All</label>
</div>
<div>
  <input type="checkbox" class="item" id="item1">
  <label for="item1">Item 1</label>
</div>
<div>
  <input type="checkbox" class="item" id="item2">
  <label for="item2">Item 2</label>
</div>
<div>
  <input type="checkbox" class="item" id="item3">
  <label for="item3">Item 3</label>
</div>
```

Write JavaScript to check or uncheck all item checkboxes when the "Select All" checkbox is toggled.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const selectAllCheckbox = document.getElementById("selectAll");
const itemCheckboxes = document.getElementsByClassName("item");

selectAllCheckbox.addEventListener("change", function() {
  for (let i = 0; i < itemCheckboxes.length; i++) {
    itemCheckboxes[i].checked = this.checked;
  }
});
```

</details>

---

## 33. Generate a Random Background Color

**Question:**  
Given:

```html
<div id="colorBox" style="width: 200px; height: 200px; border: 1px solid black;"></div>
<button id="changeColor">Change Color</button>
```

Write JavaScript to change the background color of the box to a random color when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("changeColor").addEventListener("click", function() {
  const r = Math.floor(Math.random() * 256);
  const g = Math.floor(Math.random() * 256);
  const b = Math.floor(Math.random() * 256);
  
  const randomColor = `rgb(${r}, ${g}, ${b})`;
  document.getElementById("colorBox").style.backgroundColor = randomColor;
});
```

</details>

---

## 34. Responsive Navigation Toggle

**Question:**  
Given:

```html
<button id="toggleNav">Menu</button>
<nav id="mainNav" style="display: none;">
  <ul>
    <li>Home</li>
    <li>About</li>
    <li>Contact</li>
  </ul>
</nav>
```

Write JavaScript to toggle the visibility of the navigation menu when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
document.getElementById("toggleNav").addEventListener("click", function() {
  const nav = document.getElementById("mainNav");
  
  if (nav.style.display === "none") {
    nav.style.display = "block";
    this.textContent = "Close";
  } else {
    nav.style.display = "none";
    this.textContent = "Menu";
  }
});
```

</details>

---

## 35. Create a Character Counter

**Question:**  
Given:

```html
<textarea id="message" maxlength="50" rows="4" cols="30"></textarea>
<p id="counter">50 characters remaining</p>
```

Write JavaScript to update the character counter as the user types.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const textarea = document.getElementById("message");
const counter = document.getElementById("counter");
const maxLength = textarea.maxLength;

textarea.addEventListener("input", function() {
  const remaining = maxLength - this.value.length;
  counter.textContent = `${remaining} characters remaining`;
});
```

</details>

---

## 36. Create a Simple Image Gallery Switcher

**Question:**  
Given:

```html
<div id="gallery">
  <img id="mainImage" src="image1.jpg" alt="Image 1" style="width: 300px; height: 200px;">
</div>
<div id="thumbnails">
  <img src="image1.jpg" alt="Thumbnail 1" class="thumb" data-src="image1.jpg">
  <img src="image2.jpg" alt="Thumbnail 2" class="thumb" data-src="image2.jpg">
  <img src="image3.jpg" alt="Thumbnail 3" class="thumb" data-src="image3.jpg">
</div>
```

Write JavaScript to update the main image when a thumbnail is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const mainImage = document.getElementById("mainImage");
const thumbnails = document.querySelectorAll(".thumb");

thumbnails.forEach(thumbnail => {
  thumbnail.addEventListener("click", function() {
    const newSrc = this.getAttribute("data-src");
    mainImage.src = newSrc;
    mainImage.alt = this.alt.replace("Thumbnail", "Image");
  });
});
```

</details>

---
