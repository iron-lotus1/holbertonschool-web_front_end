# HTML Advanced — Holberton School

Welcome to the **HTML Advanced** directory of the `holbertonschool-web_front_end` repository! 

This module focuses on building a modern, standard-compliant webpage skeleton using **pure HTML5** without any styling (CSS). The objective is to understand semantic tag selection, modern metadata configuration, structural hierarchy, and web standards before introducing visual styling.

---

## 📌 Project Overview

In this project, a complete webpage structure for **Techium** (a fictional digital agency) is constructed step-by-step through a series of progressive HTML files (`0-index.html` through progressive iterations).

### Key Topics Covered
- Modern **HTML5** document setup (`<!DOCTYPE html>`, `lang`, `dir` attributes).
- Document `<head>` configuration: viewports, character sets, page title, metadata descriptions, and favicons.
- **Semantic HTML5** layout tags (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`).
- Content hierarchy: Headings (`<h1>`–`<h6>`), paragraphs (`<p>`), lists (`<ul>`, `<ol>`, `<li>`), blockquotes, and inline formatting tags.
- Media elements (`<img>`, `<svg>`, `<figure>`, `<figcaption>`).
- Forms and input validation tags (`<form>`, `<label>`, `<input>`, `<button>`, `<textarea>`).

---

## 📂 Repository Structure

Below is an overview of the progression of files in this project:

| File / Step | Focus Area & Description |
| :--- | :--- |
| `0-index.html` | Basic HTML5 skeleton setup with doctype, root elements, and language attributes. |
| `1-index.html` | Addition of basic `<head>` and `<body>` tags. |
| `2-index.html` | Configuration of `<head>` metadata (charset, viewport, description, favicons). |
| `3-index.html` | Core page landmarks (`<header>`, `<main>`, `<footer>`). |
| Top-level sections | Structuring main landing page sections: Hero, Services, Works, About, News, Testimonials, Contact. |
| Structural refining | Wrapping section content with semantic tags (`<article>`, `<section>`, `<aside>`). |
| Final files | Insertion of detailed text content, links (`<a>`), images (`<img>`), buttons, and form controls. |

---

## 📄 Quick Reference & HTML Cheatsheet

Here is a cheatsheet summarizing the HTML5 elements and techniques practiced in this repository:

### 1. Document Skeleton & Metadata
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
  <!-- Character Encoding -->
  <meta charset="utf-8">
  
  <!-- Viewport for Responsive Design -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  
  <!-- Page Title & SEO Description -->
  <title>Homepage - Techium</title>
  <meta name="description" content="Techium is a digital agency.">
  
  <!-- Favicons -->
  <link rel="icon" type="image/x-icon" href="./favicon.ico">
  <link rel="icon" type="image/png" href="./favicon.png">
</head>
<body>
  <!-- Visible Content Goes Here -->
</body>
</html>
```

### 2. Semantic Page Layout (Landmarks)
Semantic HTML provides structure and improves accessibility and SEO:

| Tag | Purpose |
| :--- | :--- |
| `<header>` | Contains introductory content, logos, or main navigation. |
| `<nav>` | Wraps primary navigation links. |
| `<main>` | Represents the dominant, unique content of the `<body>`. (Only one per page). |
| `<section>` | Groups related content topically (e.g., Hero, Services, About). |
| `<article>` | Self-contained, independently reusable content (e.g., blog post, service card). |
| `<aside>` | Indirectly related content (e.g., sidebars, callout boxes). |
| `<footer>` | Page footer containing copyright info, secondary links, or contact details. |

```html
<header>
  <nav>
    <ul>
      <li><a href="#services">Services</a></li>
      <li><a href="#about">About</a></li>
    </ul>
  </nav>
</header>

<main>
  <section id="hero">
    <h1>We help business grow</h1>
  </section>
</main>

<footer>
  <p>&copy; 2026 Techium</p>
</footer>
```

### 3. Text Formatting & Hierarchy
- **Headings (`<h1>` – `<h6>`)**: Use in strict hierarchical order (`<h1>` for main title, `<h2>` for sections, `<h3>` for sub-sections). Never skip levels.
- **Paragraphs (`<p>`)**: Standard block-level text wrapper.
- **Inline Formatting**:
  - `<strong>`: Represents strong importance or urgency (bold by default).
  - `<em>`: Represents emphasized text (italic by default).
  - `<small>`: Fine print, disclaimers, or copyright text.
  - `<span>`: Generic inline container for styling/scripting.

### 4. Links & Images
```html
<!-- Hyperlink -->
<a href="https://example.com" target="_blank" rel="noopener noreferrer">Visit Website</a>

<!-- Image with accessible alt text -->
<img src="logo.png" alt="Techium Logo" width="150" height="50">

<!-- Figure with Caption -->
<figure>
  <img src="workspace.jpg" alt="Our Workspace">
  <figcaption>Techium headquarters</figcaption>
</figure>
```

### 5. Forms & Inputs
```html
<form action="#" method="post">
  <!-- Label connected to input via 'for' and 'id' -->
  <label for="user-email">Email Address:</label>
  <input type="email" id="user-email" name="email" placeholder="name@domain.com" required>

  <label for="user-message">Message:</label>
  <textarea id="user-message" name="message" rows="4"></textarea>

  <button type="submit">Send Message</button>
</form>
```

---

## 🛠️ Requirements & Validation

- All HTML files must end with a new line.
- All code must pass the **W3C HTML Validator**.
- No CSS or inline styles (`style=""`) should be present in this repository stage.
- Semantic accuracy is strictly maintained across all files.
