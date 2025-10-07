## Objective
Write scripts for variables, conditions, loops, and functions to manipulate web page content, as demonstrated in the MyGym Website project.

---

## Implementation in MyGym Website

### 1. Variables and Functions
JavaScript variables and functions are used to update content dynamically:
```html
<button id="changeTextBtn">Change Text</button>
<p id="jsText">Original text.</p>
```
```javascript
let count = 0;
function updateText() {
  count++;
  let msg = `Button clicked ${count} time${count > 1 ? 's' : ''}`;
  document.getElementById('jsText').textContent = msg;
}
document.getElementById('changeTextBtn').onclick = updateText;
```

### 2. Conditions and Loops
Conditions and loops can be used to process or display data:
```javascript
let classes = ['Cardio', 'Yoga', 'Crossfit'];
let list = '';
for (let i = 0; i < classes.length; i++) {
  if (classes[i] === 'Yoga') {
    list += `<li><b>${classes[i]}</b></li>`;
  } else {
    list += `<li>${classes[i]}</li>`;
  }
}
document.getElementById('classList').innerHTML = list;
```

### 3. DOM Manipulation
JavaScript is used to change the content of HTML elements based on user actions.

---

## How to View
Open `index.html` in your browser and interact with the buttons or elements that trigger JavaScript functions. Inspect the code to see variables, conditions, loops, and functions in use.

---

## Screenshots
-> [[Exp 6 Screenshots]]
Include screenshots showing dynamic content changes and JavaScript code for your lab record.

---

## Conclusion
This experiment demonstrates the use of JavaScript for basic programming constructs and DOM manipulation in a real web project.
