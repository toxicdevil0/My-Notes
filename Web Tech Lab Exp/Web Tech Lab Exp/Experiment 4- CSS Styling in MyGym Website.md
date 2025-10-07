## Objective
Write inline, internal, and external CSS to style HTML pages (fonts, colors, layout) as demonstrated in the MyGym Website project.

---

## Implementation in MyGym Website

### 1. External CSS
External stylesheets are linked in the `<head>` section:
```html
<link rel="stylesheet" href="css/main.css">
<link rel="stylesheet" href="css/bootstrap.min.css">
```
These files contain most of the site's styling, including layout, colors, and fonts.

### 2. Internal CSS
Internal CSS is placed within a `<style>` tag in the `<head>` or within the HTML file for specific page-level styles:
```html
<style>
  .internal-style { color: #007bff; font-weight: bold; }
</style>
```

### 3. Inline CSS
Inline CSS is applied directly to HTML elements using the `style` attribute:
```html
<p style="color: green; font-size: 18px;">This is an inline styled paragraph.</p>
```

### 4. Example Usage
- Fonts and colors are set in `main.css` and can be overridden with internal or inline CSS.
- Layout is managed using both Bootstrap (external) and custom styles.

---

## How to View
Open `index.html` and inspect elements to see the use of external, internal, and inline CSS. You can also modify these styles to observe changes.

---

## Screenshots
-> [[Exp 4 Screenshots]]
Include screenshots showing the effects of different CSS types on your website for your lab record.

---

## Conclusion
This experiment demonstrates the use of all three CSS types to style web pages, providing flexibility and control over the appearance of your site.
