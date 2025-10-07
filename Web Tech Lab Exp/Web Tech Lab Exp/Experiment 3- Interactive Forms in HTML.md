## Objective
Create interactive forms with different input types and submit buttons, as demonstrated in the MyGym Website project.

---

## Implementation in MyGym Website

### 1. Form Structure
A registration or contact form is included in `index.html` to collect user information. Example:
```html
<form id="regForm">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required>

  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required>

  <label>Gender:</label>
  <input type="radio" name="gender" value="Male"> Male
  <input type="radio" name="gender" value="Female"> Female

  <label>Interests:</label>
  <input type="checkbox" name="interests" value="Cardio"> Cardio
  <input type="checkbox" name="interests" value="Yoga"> Yoga

  <button type="submit">Submit</button>
</form>
```

### 2. Input Types Used
- **Text**: For name or other text fields
- **Email**: For email address validation
- **Radio buttons**: For gender selection
- **Checkboxes**: For selecting multiple interests
- **Submit button**: To send the form data

### 3. Form Validation (Basic)
HTML5 `required` attributes ensure that users cannot submit the form without filling mandatory fields. Additional validation can be added using JavaScript.

### 4. User Experience
The form is styled using Bootstrap classes (if available) for a better look and feel. Example:
```html
<input type="text" class="form-control" id="name" name="name" required>
```

---

## How to View
Open `index.html` in your browser and locate the registration/contact form section. Try submitting the form with and without filling all fields to observe validation.

---

## Screenshots
-> [[Exp 3 Screenshots]]
Include screenshots of the form, showing different input types and the validation messages, for your lab record.

---

## Conclusion
This experiment demonstrates how to create interactive forms in HTML, using various input types and submit buttons, as part of a real-world web project.
