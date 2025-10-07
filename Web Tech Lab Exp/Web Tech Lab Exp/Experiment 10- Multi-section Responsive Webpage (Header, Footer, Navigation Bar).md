## Objective
Design a multi-section responsive webpage with a header, footer, and navigation bar, as implemented in the MyGym Website project.

---

## Implementation in MyGym Website

### 1. Header (Navigation Bar)
The header is implemented using a fixed-top Bootstrap navigation bar at the top of the page.  
**Code from `index.html`:**
```html
<nav class="navbar navbar-expand-lg fixed-top">
  <div class="container">
    <a class="navbar-brand" href="index.html">MyGym Fitness</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false"
      aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav ml-lg-auto">
        <li class="nav-item">
          <a href="#home" class="nav-link smoothScroll">Home</a>
        </li>
        <li class="nav-item">
          <a href="#about" class="nav-link smoothScroll">About Us</a>
        </li>
        <li class="nav-item">
          <a href="#class" class="nav-link smoothScroll">Classes</a>
        </li>
        <li class="nav-item">
          <a href="#schedule" class="nav-link smoothScroll">Schedules</a>
        </li>
        <li class="nav-item">
          <a href="#contact" class="nav-link smoothScroll">Contact</a>
        </li>
      </ul>
      <ul class="social-icon ml-lg-3">
        <li><a href="#" class="fa fa-facebook"></a></li>
        <li><a href="https://x.com/Siddhi_Gupta11/communities/explore" class="fa fa-twitter"></a></li>
        <li><a href="https://www.instagram.com/gymrats_86?igsh=MWNnaGM3emFtenBvbA==" class="fa fa-instagram"></a></li>
      </ul>
    </div>
  </div>
</nav>
```

### 2. Main Sections
The main content is divided into multiple sections using `<section>` tags with unique IDs.  
**Code from `index.html`:**
```html
<!-- HERO -->
<section class="hero d-flex flex-column justify-content-center align-items-center" id="home">
  <!-- ... -->
</section>

<section class="feature" id="feature">
  <!-- ... -->
</section>

<section class="about section" id="about">
  <!-- ... -->
</section>

<section class="class section" id="class">
  <!-- ... -->
</section>

<section class="schedule section" id="schedule">
  <!-- ... -->
</section>

<section class="contact section" id="contact">
  <!-- ... -->
</section>
```

### 3. Footer
A footer is included at the bottom of the page, containing contact information and social media links.  
**Code from `index.html`:**
```html
<footer class="site-footer">
  <div class="container">
    <div class="row">
      <div class="ml-auto col-lg-4 col-md-5">
        <p class="copyright-text">Copyright &copy; Siddhi Gupta
        <br>Design with ❤️: <a href="https://github.com/Siddhii1108">Siddhi Gupta -GitHub</a></p>
      </div>
      <!-- ... -->
    </div>
  </div>
</footer>
```

### 4. Responsiveness
- The layout uses Bootstrap's grid system and utility classes to ensure the site looks good on all devices.
- The navigation bar collapses on mobile devices.

---

## How to View
Open `index.html` in your browser. The header (navigation bar) is always visible at the top. Scroll to see the different sections. The footer is at the bottom of the page.

---

## Screenshots
-> [[Exp 10 Screenshots]]
Include screenshots of the header, navigation bar, main sections, and footer for your lab record.

---

## Conclusion
This experiment demonstrates how to structure a modern, multi-section, responsive webpage using HTML and Bootstrap, with clear navigation and consistent header/footer elements.
