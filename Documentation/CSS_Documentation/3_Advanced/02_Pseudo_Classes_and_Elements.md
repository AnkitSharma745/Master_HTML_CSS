# CSS Pseudo-classes and Elements

## Pseudo-classes

### State Pseudo-classes

```css
/* User Action States */
.element:hover {
} /* Mouse over */
.element:active {
} /* Being clicked */
.element:focus {
} /* Keyboard focus */
.element:focus-visible {
} /* Visible focus */
.element:focus-within {
} /* Child has focus */

/* Form States */
input:checked {
} /* Checked inputs */
input:disabled {
} /* Disabled elements */
input:required {
} /* Required fields */
input:valid {
} /* Valid input */
input:invalid {
} /* Invalid input */
input:in-range {
} /* Value within range */
input:placeholder-shown {
} /* Showing placeholder */

/* Link States */
a:link {
} /* Unvisited links */
a:visited {
} /* Visited links */
```

### Structural Pseudo-classes

```css
/* Child Selection */
element:first-child {
}
element:last-child {
}
element:nth-child(n) {
}
element:nth-last-child(n) {
}
element:only-child {
}

/* Type Selection */
element:first-of-type {
}
element:last-of-type {
}
element:nth-of-type(n) {
}
element:nth-last-of-type(n) {
}
element:only-of-type {
}

/* Complex Patterns */
/* Every third element */
element:nth-child(3n) {
}

/* Odd elements */
element:nth-child(odd) {
}

/* Even elements */
element:nth-child(even) {
}

/* First 3 elements */
element:nth-child(-n + 3) {
}
```

### Advanced Selectors

```css
/* Negation */
:not(selector) {
}

/* Matches any specified selector */
:is(header, main, footer) p {
}

/* Matches if all selectors match */
:where(header, main, footer) p {
}

/* Empty elements */
:empty {
}

/* Root element */
:root {
}

/* Target element (URL fragment) */
:target {
}

/* Language specific */
:lang(en) {
}
```

## Pseudo-elements

### Text and Content

```css
/* First letter */
p::first-letter {
  font-size: 2em;
  float: left;
  margin-right: 0.1em;
}

/* First line */
p::first-line {
  font-variant: small-caps;
}

/* Selection */
::selection {
  background: #ffeb3b;
  color: black;
}

/* Placeholder */
input::placeholder {
  color: #666;
  font-style: italic;
}
```

### Generated Content

```css
/* Before element */
.element::before {
  content: "➡️";
  margin-right: 0.5em;
}

/* After element */
.element::after {
  content: "";
  display: block;
  clear: both;
}

/* Quotes */
q::before {
  content: "«";
}
q::after {
  content: "»";
}

/* Counter */
.list-item::before {
  counter-increment: list;
  content: counter(list);
}
```

### Modern Pseudo-elements

```css
/* File upload button */
input[type="file"]::file-selector-button {
}

/* Color picker */
input[type="color"]::color-swatch {
}

/* Scrollbar styling */
element::-webkit-scrollbar {
}
element::-webkit-scrollbar-thumb {
}
element::-webkit-scrollbar-track {
}

/* List markers */
li::marker {
  content: "🔹";
  color: blue;
}
```

## Common Use Cases

### Custom Checkbox

```css
.custom-checkbox {
  position: relative;
  padding-left: 1.5em;
}

.custom-checkbox input {
  position: absolute;
  opacity: 0;
}

.custom-checkbox::before {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  width: 1em;
  height: 1em;
  border: 2px solid currentColor;
  border-radius: 3px;
}

.custom-checkbox input:checked + ::before {
  background: currentColor;
}
```

### Tooltip

```css
.tooltip {
  position: relative;
}

.tooltip::after {
  content: attr(data-tooltip);
  position: absolute;
  bottom: 100%;
  left: 50%;
  transform: translateX(-50%);
  padding: 0.5em;
  background: black;
  color: white;
  border-radius: 4px;
  font-size: 0.875em;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.3s;
}

.tooltip:hover::after {
  opacity: 1;
}
```

### Required Field Indicator

```css
.required-field::after {
  content: "*";
  color: red;
  margin-left: 0.25em;
}

/* Alternative using :required */
input:required::after {
  content: "*";
  color: red;
}
```

## Best Practices

1. Performance

   - Use specific selectors to avoid unnecessary matching
   - Avoid excessive use of complex selectors
   - Consider reflow impact with dynamic pseudo-classes

2. Accessibility

   - Ensure proper focus states
   - Maintain color contrast
   - Don't hide important content in pseudo-elements

3. Maintainability

   - Use logical naming for custom states
   - Document complex selector patterns
   - Keep generated content minimal

4. Browser Support

   - Test across browsers
   - Provide fallbacks for modern features
   - Use vendor prefixes when needed

5. Common Patterns

```css
/* Loading State */
.button:not(:disabled):active::after {
  content: "...";
}

/* External Links */
a[href^="http"]::after {
  content: "↗️";
  display: inline-block;
  margin-left: 0.25em;
}

/* Form Validation */
input:invalid:not(:placeholder-shown) {
  border-color: red;
}

input:invalid:not(:placeholder-shown) + .error-message::before {
  content: "Please check this field";
  color: red;
  font-size: 0.875em;
}
```
