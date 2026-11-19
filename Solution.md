HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 7.1 — Responsive Navbar</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <!-- Step 1: Header containing a logo, navigation links, and a button -->
  <header class="navbar">
    <a href="#" class="logo">BrandLogo</a>

    <nav class="nav-menu">
      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <a href="#signup" class="nav-btn">Get Started</a>
    </nav>
  </header>

</body>
</html>
2. CSS (styles.css)
CSS
/* Reset default browser spacing */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: system-ui, -apple-system, sans-serif;
  background-color: #f8fafc;
}

/* Steps 2, 3, & 4: Flexbox container, horizontal spacing, and vertical alignment */
.navbar {
  display: flex;
  justify-content: space-between; /* Pushes logo to the left and nav-menu to the right */
  align-items: center;            /* Vertically centers all items */
  background-color: #0f172a;
  padding: 1rem 2.5rem;
  color: #ffffff;
}

/* Logo Styling */
.logo {
  font-size: 1.5rem;
  font-weight: 700;
  color: #ffffff;
  text-decoration: none;
  letter-spacing: -0.5px;
}

/* Navigation Wrapper */
.nav-menu {
  display: flex;
  align-items: center;
  gap: 2rem; /* Creates consistent spacing between the links and the button */
}

/* Step 5: Style navigation links */
.nav-links {
  display: flex;
  list-style: none;
  gap: 1.75rem;
}

.nav-links a {
  color: #cbd5e1;
  text-decoration: none;
  font-size: 1rem;
  font-weight: 500;
  transition: color 0.2s ease;
}

.nav-links a:hover {
  color: #38bdf8;
}

/* Step 5: Style the call-to-action button */
.nav-btn {
  background-color: #38bdf8;
  color: #0f172a;
  padding: 0.6rem 1.25rem;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.95rem;
  transition: background-color 0.2s ease, transform 0.1s ease;
}

.nav-btn:hover {
  background-color: #7dd3fc;
}

.nav-btn:active {
  transform: scale(0.98);
}

/* Step 6: Responsive adjustment for smaller browser widths */
@media (max-width: 768px) {
  .navbar {
    flex-direction: column;
    gap: 1rem;
    padding: 1.25rem;
  }

  .nav-menu {
    flex-direction: column;
    gap: 1rem;
    width: 100%;
  }

  .nav-links {
    flex-wrap: wrap;
    justify-content: center;
    gap: 1.25rem;
  }

  .nav-btn {
    text-align: center;
    width: 100%;
    max-width: 200px;
  }
}
Key Flexbox Concepts Used
display: flex: Applied to .navbar, .nav-menu, and .nav-links to arrange elements horizontally in a row by default.

justify-content: space-between: Distributes extra horizontal space so the logo stays anchored on the far left and the navigation menu stays on the far right.

align-items: center: Keeps the logo text, navigation links, and button aligned along the exact same horizontal center line regardless of their differing heights.

@media (max-width: 768px): Switches flex-direction from row to column when the viewport narrows, preventing links from overflowing or overlapping on mobile screens.