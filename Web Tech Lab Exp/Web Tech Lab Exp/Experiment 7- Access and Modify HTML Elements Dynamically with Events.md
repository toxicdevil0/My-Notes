## Objective
Access and modify HTML elements dynamically; handle events such as on click and on mouse over, as demonstrated in the MyGym Website project.

---

## Implementation in MyGym Website

### 1. Event Handling (Click and Mouseover)
JavaScript is used to add interactivity by responding to user actions like clicks and mouse movements.

#### Example: Click Event
```html
<button id="changeTextBtn">Change Text</button>
<p id="jsText">Original text.</p>
```
```javascript
document.getElementById('changeTextBtn').onclick = function() {
  document.getElementById('jsText').textContent = 'Text changed on click!';
};
```

#### Example: Mouseover and Mouseout Events
```html
<button id="hoverBtn">Hover over me</button>
<p id="hoverMsg"></p>
```
```javascript
document.getElementById('hoverBtn').addEventListener('mouseover', function() {
  document.getElementById('hoverMsg').textContent = 'Mouse is over the button!';
});
document.getElementById('hoverBtn').addEventListener('mouseout', function() {
  document.getElementById('hoverMsg').textContent = '';
});
```

### 2. Dynamic Modification of HTML Elements
- The content of `<p>` elements is updated in response to user actions.
- You can also change styles, attributes, or add/remove elements dynamically.

---

## How to View
Open `index.html` in your browser and interact with the buttons. Observe how the text changes on click and mouseover events.

---

## Screenshots
-> [[Exp 7 Screenshots]]
Include screenshots showing the dynamic changes in the web page when events are triggered for your lab record.

---

## Conclusion
This experiment demonstrates how to use JavaScript to handle user events and dynamically update HTML content, making web pages interactive and responsive to user actions.
