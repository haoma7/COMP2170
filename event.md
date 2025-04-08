# 🧪 JavaScript Events & Event Handling: Beginner Practice Exercises

---

## 1. Basic Click Event Handler

**Question:**  
Given the following HTML:

```html
<button id="myButton">Click Me</button>
<p id="output"></p>
```

Write JavaScript to display "Button clicked!" in the paragraph when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("myButton");
const output = document.getElementById("output");

button.addEventListener("click", function() {
  output.textContent = "Button clicked!";
});
```

</details>

---

## 2. Using Inline Event Handlers

**Question:**  
Modify the HTML to use an inline event handler that shows an alert when the button is clicked:

```html
<button>Click for Alert</button>
```

<details>
<summary>💡 Click to reveal answer</summary>

```html
<button onclick="alert('Button was clicked!')">Click for Alert</button>
```

</details>

---

## 3. Event Handler Property

**Question:**  
Given the HTML:

```html
<button id="greetButton">Say Hello</button>
<p id="greeting"></p>
```

Use the onclick property (not addEventListener) to show "Hello, World!" in the paragraph when clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("greetButton");
const greeting = document.getElementById("greeting");

button.onclick = function() {
  greeting.textContent = "Hello, World!";
};
```

</details>

---

## 4. Using Named Functions as Event Handlers

**Question:**  
Given:

```html
<button id="namedFunctionButton">Click Me</button>
<p id="namedOutput"></p>
```

Create a named function and use it as a click event handler for the button.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("namedFunctionButton");
const output = document.getElementById("namedOutput");

// Named function
function showMessage() {
  output.textContent = "Button was clicked!";
}

// Assign the function as event handler
button.addEventListener("click", showMessage);
```

</details>

---

## 5. Event Object Basics

**Question:**  
Given:

```html
<button id="eventInfoButton">Click for Event Info</button>
<p id="eventOutput"></p>
```

Write JavaScript to display the event type and timestamp when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("eventInfoButton");
const output = document.getElementById("eventOutput");

button.addEventListener("click", function(event) {
  output.textContent = `Event type: ${event.type}, Timestamp: ${event.timeStamp}`;
});
```

</details>

---

## 6. Using event.target

**Question:**  
Given:

```html
<button id="targetButton">Who am I?</button>
<p id="targetOutput"></p>
```

Use event.target to display the button's ID in the paragraph when clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("targetButton");
const output = document.getElementById("targetOutput");

button.addEventListener("click", function(event) {
  output.textContent = `The element with ID "${event.target.id}" was clicked`;
});
```

</details>

---

## 7. Mouse Position with event Object

**Question:**  
Given:

```html
<div id="mouseArea" style="width: 300px; height: 200px; background-color: lightblue;">
  Move your mouse here
</div>
<p id="mousePosition"></p>
```

Display the current mouse coordinates when the mouse moves over the div.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const area = document.getElementById("mouseArea");
const output = document.getElementById("mousePosition");

area.addEventListener("mousemove", function(event) {
  output.textContent = `Mouse position - X: ${event.clientX}, Y: ${event.clientY}`;
});
```

</details>

---

## 8. Preventing Default Behavior

**Question:**  
Given:

```html
<a id="exampleLink" href="https://www.example.com">Click me (won't navigate)</a>
<p id="linkOutput"></p>
```

Prevent the default navigation behavior and instead display a message when the link is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const link = document.getElementById("exampleLink");
const output = document.getElementById("linkOutput");

link.addEventListener("click", function(event) {
  event.preventDefault();
  output.textContent = "Link click was prevented!";
});
```

</details>

---

## 9. Form Submit Event

**Question:**  
Given:

```html
<form id="simpleForm">
  <input type="text" id="username" placeholder="Enter username">
  <button type="submit">Submit</button>
</form>
<p id="formOutput"></p>
```

Prevent the form submission and display the entered username.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const form = document.getElementById("simpleForm");
const output = document.getElementById("formOutput");

form.addEventListener("submit", function(event) {
  event.preventDefault();
  const username = document.getElementById("username").value;
  output.textContent = `Form submitted with username: ${username}`;
});
```

</details>

---

## 10. Keyboard Events - keydown

**Question:**  
Given:

```html
<input type="text" id="keyInput" placeholder="Type here">
<p id="keyOutput"></p>
```

Display which key was pressed when typing in the input field.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const input = document.getElementById("keyInput");
const output = document.getElementById("keyOutput");

input.addEventListener("keydown", function(event) {
  output.textContent = `Key pressed: ${event.key}, Key code: ${event.keyCode}`;
});
```

</details>

---

## 11. Keyboard Events - keyup vs keydown

**Question:**  
Given:

```html
<input type="text" id="keyTestInput" placeholder="Type here">
<div>
  <p id="keyDownOutput">Keydown: </p>
  <p id="keyUpOutput">Keyup: </p>
</div>
```

Show the difference between keydown and keyup events by displaying the input value at both events.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const input = document.getElementById("keyTestInput");
const keyDownOutput = document.getElementById("keyDownOutput");
const keyUpOutput = document.getElementById("keyUpOutput");

input.addEventListener("keydown", function() {
  keyDownOutput.textContent = `Keydown: ${this.value}`;
});

input.addEventListener("keyup", function() {
  keyUpOutput.textContent = `Keyup: ${this.value}`;
});
```

</details>

---

## 12. Event Bubbling Basics

**Question:**  
Given:

```html
<div id="outer" style="background-color: lightblue; padding: 20px;">
  OUTER
  <div id="inner" style="background-color: lightpink; padding: 10px;">
    INNER
  </div>
</div>
<p id="bubbleOutput"></p>
```

Demonstrate event bubbling by showing which element was clicked and which element's event handler executed.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const outer = document.getElementById("outer");
const inner = document.getElementById("inner");
const output = document.getElementById("bubbleOutput");

outer.addEventListener("click", function(event) {
  output.textContent = `Outer div handler: You clicked on ${event.target.id}`;
});

inner.addEventListener("click", function(event) {
  output.textContent = `Inner div handler: You clicked on ${event.target.id}`;
});
```

</details>

---

## 13. Stopping Event Propagation

**Question:**  
Given:

```html
<div id="container" style="background-color: lightgray; padding: 20px;">
  CONTAINER
  <button id="stopButton">Click to Stop Propagation</button>
</div>
<p id="propagationOutput"></p>
```

Stop the click event from propagating to the parent element.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const container = document.getElementById("container");
const button = document.getElementById("stopButton");
const output = document.getElementById("propagationOutput");

container.addEventListener("click", function() {
  output.textContent = "Container click detected";
});

button.addEventListener("click", function(event) {
  event.stopPropagation();
  output.textContent = "Button click detected (propagation stopped)";
});
```

</details>

---

## 14. Event Delegation

**Question:**  
Given:

```html
<ul id="taskList">
  <li>Task 1</li>
  <li>Task 2</li>
  <li>Task 3</li>
</ul>
<p id="taskOutput"></p>
```

Use event delegation to handle clicks on any list item and display which task was clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const taskList = document.getElementById("taskList");
const output = document.getElementById("taskOutput");

taskList.addEventListener("click", function(event) {
  // Check if a list item was clicked
  if (event.target.tagName === "LI") {
    output.textContent = `You clicked: ${event.target.textContent}`;
  }
});
```

</details>

---

## 15. Toggle Button States

**Question:**  
Given:

```html
<button id="toggleButton">ON</button>
```

Toggle between "ON" and "OFF" text when the button is clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("toggleButton");

button.addEventListener("click", function() {
  if (this.textContent === "ON") {
    this.textContent = "OFF";
  } else {
    this.textContent = "ON";
  }
});
```

</details>

---

## 16. Mouse Events: mouseenter and mouseleave

**Question:**  
Given:

```html
<div id="hoverBox" style="width: 200px; height: 100px; background-color: lightgray;">
  Hover over me
</div>
<p id="hoverStatus">Mouse is outside the box</p>
```

Change the status text when the mouse enters and leaves the box.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const box = document.getElementById("hoverBox");
const status = document.getElementById("hoverStatus");

box.addEventListener("mouseenter", function() {
  status.textContent = "Mouse is inside the box";
});

box.addEventListener("mouseleave", function() {
  status.textContent = "Mouse is outside the box";
});
```

</details>

---

## 17. Focus and Blur Events

**Question:**  
Given:

```html
<input type="text" id="focusInput" placeholder="Click here">
<p id="focusStatus">Input is not focused</p>
```

Update the status message when the input field gains and loses focus.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const input = document.getElementById("focusInput");
const status = document.getElementById("focusStatus");

input.addEventListener("focus", function() {
  status.textContent = "Input is focused";
});

input.addEventListener("blur", function() {
  status.textContent = "Input lost focus";
});
```

</details>

---

## 18. Change Event for Form Controls

**Question:**  
Given:

```html
<select id="colorSelect">
  <option value="">Choose a color</option>
  <option value="red">Red</option>
  <option value="green">Green</option>
  <option value="blue">Blue</option>
</select>
<div id="colorBox" style="width: 100px; height: 100px; margin-top: 10px;"></div>
```

Change the color of the box when a different option is selected from the dropdown.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const select = document.getElementById("colorSelect");
const box = document.getElementById("colorBox");

select.addEventListener("change", function() {
  box.style.backgroundColor = this.value;
});
```

</details>

---

## 19. Double Click Event

**Question:**  
Given:

```html
<button id="doubleClickBtn">Double-click me</button>
<p id="doubleClickOutput"></p>
```

Display a message when the button is double-clicked.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("doubleClickBtn");
const output = document.getElementById("doubleClickOutput");

button.addEventListener("dblclick", function() {
  output.textContent = "Double click detected!";
});
```

</details>

---

## 20. Context Menu Event (Right-click)

**Question:**  
Given:

```html
<div id="rightClickArea" style="width: 200px; height: 100px; background-color: lightblue;">
  Right-click in this area
</div>
<p id="contextOutput"></p>
```

Prevent the default context menu and display a message when right-clicking in the area.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const area = document.getElementById("rightClickArea");
const output = document.getElementById("contextOutput");

area.addEventListener("contextmenu", function(event) {
  event.preventDefault();
  output.textContent = "Custom context action triggered!";
});
```

</details>

---

## 21. Event Listener with Options Parameter

**Question:**  
Given:

```html
<button id="onceButton">Click Me (I only work once)</button>
<p id="onceOutput"></p>
```

Create an event listener that only triggers once, using the options parameter.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("onceButton");
const output = document.getElementById("onceOutput");

button.addEventListener("click", function() {
  output.textContent = "Button was clicked! This handler won't run again.";
}, { once: true });
```

</details>

---

## 22. Detecting Multiple Key Presses

**Question:**  
Given:

```html
<div id="keyStatus" style="width: 300px; height: 100px; border: 1px solid black; padding: 10px;">
  Press Shift+A
</div>
```

Detect when the Shift key and the 'A' key are pressed simultaneously.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const statusElement = document.getElementById("keyStatus");

document.addEventListener("keydown", function(event) {
  if (event.key === "A" && event.shiftKey) {
    statusElement.textContent = "Success! You pressed Shift+A";
    statusElement.style.backgroundColor = "lightgreen";
  }
});
```

</details>

---

## 23. Scroll Event

**Question:**  
Given:

```html
<div style="height: 200vh;">
  <div id="scrollStatus" style="position: fixed; top: 10px; right: 10px; padding: 10px; background: white; border: 1px solid black;">
    Scroll position: 0
  </div>
</div>
```

Update the status to show the current scroll position as the user scrolls the page.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const statusElement = document.getElementById("scrollStatus");

window.addEventListener("scroll", function() {
  const scrollPosition = window.scrollY;
  statusElement.textContent = `Scroll position: ${scrollPosition}`;
});
```

</details>

---

## 24. Input Event for Real-time Form Validation

**Question:**  
Given:

```html
<input type="text" id="passwordInput" placeholder="Enter password">
<p id="passwordStrength">Password strength: N/A</p>
```

Show password strength in real-time as the user types (simple version: <6 chars = weak, 6-10 = medium, >10 = strong).

<details>
<summary>💡 Click to reveal answer</summary>

```js
const passwordInput = document.getElementById("passwordInput");
const strengthOutput = document.getElementById("passwordStrength");

passwordInput.addEventListener("input", function() {
  const length = this.value.length;
  let strength = "weak";
  
  if (length === 0) {
    strength = "N/A";
  } else if (length > 10) {
    strength = "strong";
  } else if (length >= 6) {
    strength = "medium";
  }
  
  strengthOutput.textContent = `Password strength: ${strength}`;
});
```

</details>

---

## 25. Using currentTarget vs target

**Question:**  
Given:

```html
<div id="outer" style="background-color: lightgray; padding: 20px;">
  <p>OUTER DIV</p>
  <div id="inner" style="background-color: lightblue; padding: 10px;">
    <p>INNER DIV</p>
  </div>
</div>
<p id="eventTargetOutput"></p>
```

Show the difference between event.target and event.currentTarget when clicking on various elements.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const outer = document.getElementById("outer");
const output = document.getElementById("eventTargetOutput");

outer.addEventListener("click", function(event) {
  output.textContent = `
    target: ${event.target.id || event.target.tagName}
    currentTarget: ${event.currentTarget.id}
  `;
});
```

</details>

---

## 26. Event Listener with Capture Phase

**Question:**  
Given:

```html
<div id="parent" style="background-color: lightblue; padding: 20px;">
  PARENT
  <div id="child" style="background-color: lightpink; padding: 10px;">
    CHILD
  </div>
</div>
<p id="phaseOutput"></p>
```

Use the capture phase to handle the event during the capturing phase instead of the bubbling phase.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const parent = document.getElementById("parent");
const child = document.getElementById("child");
const output = document.getElementById("phaseOutput");

// Regular bubbling phase handler (default)
child.addEventListener("click", function() {
  output.textContent += "Child handler (bubbling phase) executed\n";
});

// Capture phase handler
parent.addEventListener("click", function() {
  output.textContent = "Parent handler (capture phase) executed\n";
}, { capture: true });  // true enables capture phase
```

</details>

---

## 27. Load Event for Images

**Question:**  
Given:

```html
<img id="myImage" src="https://via.placeholder.com/300" alt="Placeholder image">
<p id="imageStatus">Loading image...</p>
```

Update the status when the image has finished loading.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const image = document.getElementById("myImage");
const status = document.getElementById("imageStatus");

image.addEventListener("load", function() {
  status.textContent = "Image loaded successfully!";
});

image.addEventListener("error", function() {
  status.textContent = "Error loading image!";
});
```

</details>

---

## 28. Using Multiple Event Types

**Question:**  
Given:

```html
<button id="multiEventBtn">Hover and Click Me</button>
<p id="multiEventOutput"></p>
```

Add multiple event types to the same element, showing different messages for mouse over, out, and click.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("multiEventBtn");
const output = document.getElementById("multiEventOutput");

button.addEventListener("mouseover", function() {
  output.textContent = "Mouse is over the button";
});

button.addEventListener("mouseout", function() {
  output.textContent = "Mouse left the button";
});

button.addEventListener("click", function() {
  output.textContent = "Button was clicked!";
});
```

</details>

---

## 29. Drag and Drop Basics

**Question:**  
Given:

```html
<div id="draggable" draggable="true" style="width: 100px; height: 100px; background-color: lightblue;">
  Drag me
</div>
<div id="dropzone" style="width: 200px; height: 200px; background-color: lightgray; margin-top: 10px;">
  Drop here
</div>
<p id="dragStatus"></p>
```

Implement basic drag and drop functionality.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const draggable = document.getElementById("draggable");
const dropzone = document.getElementById("dropzone");
const status = document.getElementById("dragStatus");

// Drag events for the draggable element
draggable.addEventListener("dragstart", function() {
  status.textContent = "Dragging started";
  this.style.opacity = "0.5";
});

draggable.addEventListener("dragend", function() {
  status.textContent = "Dragging ended";
  this.style.opacity = "1";
});

// Drop events for the dropzone
dropzone.addEventListener("dragover", function(event) {
  // Prevent default to allow drop
  event.preventDefault();
});

dropzone.addEventListener("drop", function(event) {
  event.preventDefault();
  status.textContent = "Item dropped!";
  this.style.backgroundColor = "lightgreen";
});
```

</details>

---

## 30. Resize Event

**Question:**  
Given:

```html
<div id="windowSize" style="position: fixed; top: 10px; left: 10px; background: white; padding: 5px; border: 1px solid black;">
  Window size: 
</div>
```

Display the current window dimensions and update when the window is resized.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const sizeDisplay = document.getElementById("windowSize");

// Update on load
updateSize();

// Update when window is resized
window.addEventListener("resize", updateSize);

function updateSize() {
  const width = window.innerWidth;
  const height = window.innerHeight;
  sizeDisplay.textContent = `Window size: ${width}px × ${height}px`;
}
```

</details>

---

## 31. Using Event.key vs Event.code

**Question:**  
Given:

```html
<input type="text" id="keyCodeInput" placeholder="Press any key">
<div>
  <p id="keyOutput"></p>
  <p id="codeOutput"></p>
</div>
```

Show the difference between event.key and event.code when pressing keyboard keys.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const input = document.getElementById("keyCodeInput");
const keyOutput = document.getElementById("keyOutput");
const codeOutput = document.getElementById("codeOutput");

input.addEventListener("keydown", function(event) {
  keyOutput.textContent = `event.key: "${event.key}" (character produced)`;
  codeOutput.textContent = `event.code: "${event.code}" (physical key position)`;
});
```

</details>

---

## 32. Touch Events Basics

**Question:**  
Given:

```html
<div id="touchArea" style="width: 300px; height: 200px; background-color: lightblue; user-select: none;">
  Touch area (for touch devices)
</div>
<p id="touchOutput">Touch status: none</p>
```

Handle basic touch events to show when touches start and end.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const touchArea = document.getElementById("touchArea");
const output = document.getElementById("touchOutput");

touchArea.addEventListener("touchstart", function(event) {
  output.textContent = `Touch started with ${event.touches.length} finger(s)`;
});

touchArea.addEventListener("touchend", function() {
  output.textContent = "Touch ended";
});

touchArea.addEventListener("touchmove", function(event) {
  // Prevent scrolling while touching the element
  event.preventDefault();
  output.textContent = "Touch moving";
});
```

</details>

---

## 33. Pointer Events

**Question:**  
Given:

```html
<canvas id="drawCanvas" width="300" height="200" style="border: 1px solid black;"></canvas>
<p>Draw on the canvas (works with mouse and touch)</p>
```

Use pointer events to create a simple drawing application that works with both mouse and touch.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const canvas = document.getElementById("drawCanvas");
const ctx = canvas.getContext("2d");
let isDrawing = false;

// Start drawing
canvas.addEventListener("pointerdown", function(event) {
  isDrawing = true;
  draw(event);
});

// Stop drawing
canvas.addEventListener("pointerup", function() {
  isDrawing = false;
  ctx.beginPath(); // Start a new path next time we draw
});

canvas.addEventListener("pointerout", function() {
  isDrawing = false;
  ctx.beginPath(); // Start a new path next time we draw
});

// Draw
canvas.addEventListener("pointermove", function(event) {
  if (isDrawing) {
    draw(event);
  }
});

function draw(event) {
  // Get canvas position
  const rect = canvas.getBoundingClientRect();
  
  // Calculate position within canvas
  const x = event.clientX - rect.left;
  const y = event.clientY - rect.top;
  
  ctx.lineWidth = 5;
  ctx.lineCap = "round";
  ctx.strokeStyle = "black";
  
  ctx.lineTo(x, y);
  ctx.stroke();
  ctx.beginPath();
  ctx.moveTo(x, y);
}
```

</details>



---

## 34. Removing Event Listeners

**Question:**  
Given:

```html
<button id="clickButton">Click me multiple times</button>
<button id="removeListener">Remove click listener</button>
<p id="clickCount">Clicks: 0</p>
```

Create a button that counts clicks and another button to remove the click event listener.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const clickButton = document.getElementById("clickButton");
const removeButton = document.getElementById("removeListener");
const clickDisplay = document.getElementById("clickCount");
let clicks = 0;

// Named function so we can remove it later
function countClick() {
  clicks++;
  clickDisplay.textContent = `Clicks: ${clicks}`;
}

// Add the event listener
clickButton.addEventListener("click", countClick);

// Button to remove the listener
removeButton.addEventListener("click", function() {
  clickButton.removeEventListener("click", countClick);
  this.textContent = "Listener removed";
  this.disabled = true;
});
```

</details>

---

## 35. Mouse Wheel/Scroll Events

**Question:**  
Given:

```html
<div id="scrollBox" style="width: 200px; height: 200px; border: 1px solid black; overflow: auto;">
  <div style="height: 400px; background: linear-gradient(to bottom, red, blue);">
    Scroll me
  </div>
</div>
<p id="scrollInfo"></p>
```

Display information about scroll direction when the user scrolls inside the box.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const scrollBox = document.getElementById("scrollBox");
const info = document.getElementById("scrollInfo");

scrollBox.addEventListener("wheel", function(event) {
  // Prevent the page from scrolling when the box is scrolled
  event.preventDefault();
  
  const direction = event.deltaY > 0 ? "down" : "up";
  info.textContent = `Scrolling ${direction}`;
  
  // Manual scroll the box
  this.scrollTop += event.deltaY;
});
```

</details>

---

## 36. Event Listener with Arrow Function

**Question:**  
Given:

```html
<button id="thisButton">Click to see 'this'</button>
<p id="thisOutput"></p>
```

Compare regular function and arrow function behavior with 'this' in event handlers.

<details>
<summary>💡 Click to reveal answer</summary>

```js
const button = document.getElementById("thisButton");
const output = document.getElementById("thisOutput");

// Regular function - 'this' refers to the element
button.addEventListener("click", function() {
  output.textContent = "'this' in regular function is: " + this.id;
});

// Add arrow function handler after 2 seconds
setTimeout(() => {
  // Arrow function - 'this' doesn't reference the element
  button.addEventListener("click", (event) => {
    output.textContent = "'this' in arrow function is NOT the element. We need to use event.target: " + event.target.id;
  });
}, 2000);
```

</details>

---
