---

# Semantic HTML

## 1. Introduction to Semantic HTML
Semantic HTML refers to the use of HTML tags that convey the *meaning* of their content, not just their appearance. These elements improve accessibility, SEO, and code maintainability.

### Why Use Semantic HTML?
- **Improved Accessibility:** Screen readers can better interpret content.
- **Better SEO:** Search engines understand content structure.
- **Readability:** Clean and self-explanatory code.

---

## 2. Common Semantic HTML Elements

### a. Structural Elements

- **`<header>`**: Defines the top section or heading of a page.
- **`<nav>`**: Contains navigation links.
- **`<main>`**: Represents the main content.
- **`<section>`**: Groups related content.
- **`<article>`**: Represents self-contained content.
- **`<footer>`**: Defines footer content.

### b. Text-Level Semantics

- **`<strong>`**: Strong emphasis (bold).
- **`<em>`**: Emphasis (italic).
- **`<abbr>`**: Abbreviation.
- **`<blockquote>`**: Block-level quotation.

### c. Media Elements

- **`<figure>`**: Groups media elements.
- **`<figcaption>`**: Caption for a `<figure>`.

**Example:**

```html
<header>
  <h1>Welcome to My Blog</h1>
</header>
<nav>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
  </ul>
</nav>
<main>
  <section>
    <article>
      <h2>Article Title</h2>
      <p>This is an example of a semantic HTML structure.</p>
    </article>
  </section>
</main>
<footer>
  <p>&copy; 2024 My Blog</p>
</footer>
```

---

## 3. Accessibility with Semantic HTML

- Use **`aria-*`** attributes when semantics alone are not enough.
- Provide descriptive **alt** attributes for images.
- Ensure form labels are properly associated with inputs.

**Example:**

```html
<form>
  <label for="email">Email:</label>
  <input type="email" id="email" aria-required="true" />
</form>
```

---

## 4. SEO and Semantic HTML

Search engines rely on semantic tags to understand the structure and context of a page.

### Best Practices:

- Use **`<h1>`** for primary page titles.
- Organize content with **`<section>`** and **`<article>`**.
- Use descriptive **meta tags**.

---

## 5. Best Practices for Semantic HTML

- Avoid using `<div>` and `<span>` for structural content.
- Ensure proper nesting of elements.
- Validate HTML code using tools like **W3C Markup Validation Service**.

---

## 6. Modern Libraries Supporting Semantic HTML

### a. **Accessible Rich Internet Applications (ARIA)**

- Enhances HTML semantics for complex UIs.

### b. **React Accessibility Tools**

- Helps ensure semantic practices in React apps.

### c. **Semantic UI**

- Provides pre-designed semantic components.

**Why Use These Tools?**

- Enhance accessibility.
- Simplify semantic implementation.
- Improve SEO and user experience.

---

## 7. Conclusion

Semantic HTML is a fundamental building block of modern web development. It enhances accessibility, improves SEO, and ensures that your code is clean and maintainable.

_Next Step: Explore integration with frameworks and tools like ARIA and React Accessibility Tools._

---
