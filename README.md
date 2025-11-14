# GoIT Markup Homework #3: Layout & Flexbox

## Description of the Assignment

This repository contains the solution for GoIT Markup Homework #3. This assignment builds directly on the styled elements from Homework #2, with the primary goal of implementing a full page layout using **Flexbox** and precise spacing.

The main focus was to transition from a simple vertical flow to a structured, multi-column layout. This involved adding a global container, resetting default browser styles, connecting `modern-normalize`, and applying Flexbox to arrange elements horizontally. A significant part of the work was calculating and applying correct `padding`, `margin`, and `gap` values to match the design layout.

---

## 🛠️ Key Technical Implementations

The following key layout solutions were implemented:

### 1. Project Setup & Normalization

* **Modern Normalize:** The `modern-normalize.css` library was linked in the `<head>` (before the main `styles.css`) to ensure consistent styling across all browsers.
* **Global Resets:** Default browser `margin` and `padding` were reset for `h1-h6`, `p`, and `ul` elements.
* **Image Behavior:** `img` tags were set to `display: block` to remove default inline spacing.

### 2. The `.container` Class

A central, reusable `.container` class was created to manage the main content width and centering.

* **Purpose:** Wraps the content inside the `header`, `footer`, and all `section` elements.
* **Properties:**
    * `width: 1158px`
    * `padding: 0 15px`
    * `margin: 0 auto` (to center the container on the page)

### 3. Flexbox Layouts

`display: flex` was the primary tool used to structure the page:

* **Header:** Used on the main container to separate the `<nav>` and `<address>` blocks. It was also used on the navigation `<ul>` and contacts `<ul>` to align their items horizontally, with a `gap: 40px`.
* **Section Lists:** All `<ul>` elements in the "Features," "Our Team," and "Our Portfolio" sections were converted to flex containers (`display: flex`) to arrange their `<li>` items in a row.
* **Gaps:** The `gap` property (or `column-gap` / `row-gap`) was used to manage the space between flex items (e.g., `gap: 24px` for the "Features" list).
* **Portfolio Grid (`flex-wrap`):** The "Our Portfolio" list (`<ul>`) uses `flex-wrap: wrap` to allow the items to wrap onto the next line, creating a 3-column grid.

### 4. Dynamic Sizing with `calc()`

The `calc()` function was used to create responsive column widths that respect the `gap` between them:

* **4-Column Layout (Features/Team):**
    * `width: calc((100% - 72px) / 4);` *(100% width - 3 gaps of 24px) / 4 items*
* **3-Column Layout (Portfolio):**
    * `width: calc((100% - 48px) / 3);` *(100% width - 2 gaps of 24px) / 3 items*

### 5. Spacing & Styling Details

* **Section Spacing:** Sections now have vertical `padding` (e.g., `padding: 120px 0`) to create space around their content, rather than using `margin`.
* **Element Spacing:** `margin-bottom` was used to create space *between* elements inside sections (e.g., `margin-bottom: 72px` on section titles).
* **Visual Details:**
    * Added a `border-bottom: 1px solid #e7e9fc` to the `<header>`.
    * Styled "Our Team" cards with `border-radius: 0px 0px 4px 4px;`.
    * Styled "Our Portfolio" cards with a `border: 1px solid #e7e9fc;` (and `border-top: none;`) on the text content block.
* **Accessibility:** Implemented the `.visually-hidden` class to hide the `<h2>` in the "Features" section from view while keeping it accessible to screen readers.

---

## 🚀 Live Page

The project is hosted on GitHub Pages. You can view the live result here:

**[https://idziamko.github.io/goit-markup-hw-03/]**
