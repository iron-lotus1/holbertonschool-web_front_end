# 🌐 HTML & CSS Quick Reference Cheatsheet

A practical, structured reference guide for semantic HTML5 and modern CSS3 layouts, tailored for front-end engineering projects in the Holberton School curriculum.

---

## 📑 Table of Contents
- [HTML5 Document Boilerplate](#-html5-document-boilerplate)
- [Semantic HTML5 Elements](#-semantic-html5-elements)
- [Forms & Media](#-forms--media)
- [CSS Selectors & Specificity](#-css-selectors--specificity)
- [The Box Model](#-the-box-model)
- [Positioning](#-positioning)
- [Flexbox Layout](#-flexbox-layout)
- [CSS Grid Layout](#-css-grid-layout)
- [Variables & Responsive Design](#-variables--responsive-design)

---

## 🏗️ HTML5 Document Boilerplate

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Page description for SEO">
  <title>Document Title</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>...</header>
  <main>...</main>
  <footer>...</footer>
</body>
</html>
```

---

## 🧱 Semantic HTML5 Elements

Use semantic tags instead of generic `<div>` wrappers to improve accessibility (a11y) and SEO.

| Tag | Purpose |
| :--- | :--- |
| `<header>` | Introductory content, logos, or top-level navigation. |
| `<nav>` | Major navigation link blocks. |
| `<main>` | Dominant, unique content of the `<body>` (use only once per page). |
| `<section>` | Thematic grouping of content, typically with a heading. |
| `<article>` | Self-contained, independently distributable content (blog post, card). |
| `<aside>` | Tangentially related content (sidebars, callout boxes). |
| `<footer>` | Authorship, copyright, contact info, or secondary links. |
| `<figure>` / `<figcaption>` | Self-contained media (images, code snippets) with an optional caption. |

---

## 📝 Forms & Media

### Accessible Form Structure
```html
<form action="/submit" method="POST">
  <label for="email">Email Address:</label>
  <input type="email" id="email" name="email" placeholder="you@example.com" required>

  <label for="role">Role:</label>
  <select id="role" name="role">
    <option value="dev">Developer</option>
    <option value="sysadmin">SysAdmin</option>
  </select>

  <button type="submit">Submit</button>
</form>
```

### Common Input Types & Attributes
* **Types:** `text`, `email`, `password`, `number`, `tel`, `url`, `date`, `checkbox`, `radio`, `file`, `search`
* **Validation & UX:** `required`, `disabled`, `readonly`, `minlength` / `maxlength`, `pattern="[A-Za-z]{3}"`, `autocomplete`

### Media Tags
```html
<!-- Always include alt text for screen readers and broken image fallbacks -->
<img src="image.webp" alt="Descriptive text" width="800" height="600" loading="lazy">

<video controls width="640" poster="thumbnail.jpg">
  <source src="video.mp4" type="video/mp4">
</video>
```

---

## 🎯 CSS Selectors & Specificity

### Core Selectors
| Selector | Example | Targets |
| :--- | :--- | :--- |
| **Universal** | `*` | All elements on the page. |
| **Element** | `p` | All `<p>` elements. |
| **Class** | `.btn-primary` | All elements with `class="btn-primary"`. |
| **ID** | `#main-header` | The unique element with `id="main-header"`. |
| **Attribute** | `input[type="text"]` | `<input>` elements with a specific attribute/value. |
| **Descendant** | `nav a` | Any `<a>` nested anywhere inside `<nav>`. |
| **Direct Child** | `ul > li` | `<li>` elements that are immediate children of `<ul>`. |
| **Adjacent Sibling** | `h1 + p` | The `<p>` immediately following an `<h1>`. |
| **Pseudo-class** | `a:hover`, `li:nth-child(odd)` | Elements in a specific state or structural position. |
| **Pseudo-element** | `p::before`, `p::after` | Virtual elements injected before/after content (requires `content: ""`). |

### Specificity Hierarchy (Lowest to Highest)
1. **Elements & Pseudo-elements:** `div`, `::before` `(0, 0, 1)`
2. **Classes, Attributes & Pseudo-classes:** `.card`, `[type="text"]`, `:hover` `(0, 1, 0)`
3. **IDs:** `#navbar` `(1, 0, 0)`
4. **Inline Styles:** `style="color: red;"` `(1, 0, 0, 0)`
5. **`!important`:** Overrides everything (use sparingly as a last resort).

---

## 📦 The Box Model

Every element is rendered as a rectangular box consisting of: **Content $\rightarrow$ Padding $\rightarrow$ Border $\rightarrow$ Margin**.

```css
/* Best Practice Reset: Ensures padding and borders don't inflate element widths */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

### Shorthand Syntax
* `margin: 10px;` $\rightarrow$ All 4 sides
* `margin: 10px 20px;` $\rightarrow$ Top/Bottom | Left/Right
* `margin: 10px 20px 30px;` $\rightarrow$ Top | Left/Right | Bottom
* `margin: 10px 20px 30px 40px;` $\rightarrow$ Top | Right | Bottom | Left *(Clockwise)*

---

## 📍 Positioning

| Value | Behavior |
| :--- | :--- |
| `static` | Default document flow. `top`, `right`, `bottom`, `left`, and `z-index` have no effect. |
| `relative` | Offset relative to its normal position; original space in document flow is preserved. |
| `absolute` | Removed from normal flow; positioned relative to its nearest **non-static** ancestor. |
| `fixed` | Removed from normal flow; pinned relative to the browser viewport (stays on scroll). |
| `sticky` | Toggles between `relative` and `fixed` based on scroll threshold (e.g., `top: 0`). |

---

## 📐 Flexbox Layout

Ideal for **1-dimensional** layouts (a single row or a single column).

### Parent Container Properties
```css
.flex-container {
  display: flex;
  flex-direction: row;            /* row | row-reverse | column | column-reverse */
  flex-wrap: wrap;                /* nowrap | wrap | wrap-reverse */
  justify-content: space-between; /* Main axis: flex-start | center | flex-end | space-between | space-around | space-evenly */
  align-items: center;            /* Cross axis: stretch | flex-start | center | flex-end | baseline */
  gap: 1rem;                      /* Space between flex items */
}
```

### Child Item Properties
```css
.flex-item {
  flex: 1 1 200px;   /* Shorthand: flex-grow | flex-shrink | flex-basis */
  align-self: auto;  /* Overrides container's align-items for this specific item */
  order: 0;          /* Controls visual order without changing HTML */
}
```

---

## 🕸️ CSS Grid Layout

Ideal for **2-dimensional** layouts (controlling rows and columns simultaneously).

### Parent Container Properties
```css
.grid-container {
  display: grid;
  /* Responsive auto-fitting columns without media queries */
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  grid-template-rows: auto 1fr auto;
  gap: 1.5rem;                  /* Shorthand for row-gap and column-gap */
  justify-items: stretch;       /* Horizontal alignment inside cells */
  align-items: stretch;         /* Vertical alignment inside cells */
}
```

### Child Item Placement
```css
.grid-item {
  grid-column: 1 / 3;           /* Spans from column line 1 to 3 (or use: span 2) */
  grid-row: 1 / 2;              /* Spans from row line 1 to 2 */
}
```

---

## 🎨 Variables & Responsive Design

### CSS Custom Properties (Variables)
```css
:root {
  --primary-color: #2563eb;
  --bg-dark: #0f172a;
  --spacing-md: 1rem;
  --font-main: system-ui, -apple-system, sans-serif;
}

body {
  background-color: var(--bg-dark);
  font-family: var(--font-main);
  padding: var(--spacing-md);
}
```

### Relative Units
* `rem` — Relative to the root `<html>` font-size (usually `16px`). Best for font sizes and spacing.
* `em` — Relative to the parent element's font-size.
* `vw` / `vh` — `1%` of the viewport's width or height.
* `%` — Relative to the parent element's dimensions.

### Mobile-First Media Queries
Write base styles for mobile devices first, then scale up using `min-width`:
```css
/* Base styles (Mobile: < 768px) */
.container {
  padding: 1rem;
}

/* Tablet (≥ 768px) */
@media (min-width: 768px) {
  .container {
    padding: 2rem;
  }
}

/* Desktop (≥ 1024px) */
@media (min-width: 1024px) {
  .container {
    max-width: 1200px;
    margin: 0 auto;
  }
}
```
