## Objective
Implement box model, positioning, and CSS Flexbox for responsive layouts in the MyGym Website project.

---

## Implementation in MyGym Website

### 1. Box Model
The box model is demonstrated using CSS properties like `margin`, `border`, `padding`, and `width`:
```html
<div class="box-model">This box demonstrates the CSS box model.</div>
```
```css
.box-model {
  margin: 10px;
  border: 5px solid #333;
  padding: 15px;
  background: #eee;
}
```

### 2. Positioning
CSS positioning is used to move elements relative to their normal position:
```html
<div class="positioned">This box is positioned using relative positioning.</div>
```
```css
.positioned {
  position: relative;
  left: 20px;
  top: 10px;
  background: #d1e7dd;
}
```

### 3. Flexbox
Flexbox is used for responsive layouts and alignment:
```html
<div class="flex-container">
  <div class="flex-item">Flex Item 1</div>
  <div class="flex-item">Flex Item 2</div>
  <div class="flex-item">Flex Item 3</div>
</div>
```
```css
.flex-container {
  display: flex;
  gap: 20px;
}
.flex-item {
  background: #f8f9fa;
  padding: 10px;
  border: 1px solid #ccc;
}
```

---

## How to View
Open `index.html` and look for sections or elements styled with the above classes. Resize the browser window to see Flexbox responsiveness.

---

## Screenshots
-> [[Exp 5 Screenshots]]
Include screenshots of the box model, positioned elements, and Flexbox layout for your lab record.

---

## Conclusion
This experiment demonstrates the use of the CSS box model, positioning, and Flexbox to create visually appealing and responsive layouts.
