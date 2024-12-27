# Syntax and Selectors

## 1. CSS Syntax

### Basic Structure

```css
selector {
  property: value;
}
```

- **Selector:** Targets HTML elements.
- **Property:** The style property to be modified.
- **Value:** The value assigned to the property.

### Example

```css
h1 {
  color: blue;
  font-size: 24px;
}
```

## 2. Types of CSS Selectors

### 2.1 Basic Selectors

- **Universal Selector (`*`)**: Targets all elements.
- **Type Selector (`h1`)**: Targets specific elements.
- **Class Selector (`.class`)**: Targets elements with a specific class.
- **ID Selector (`#id`)**: Targets elements with a specific ID.
- **Group Selector (`h1, p`)**: Targets multiple elements.

### Example

```css
* {
  margin: 0;
}
h1 {
  color: red;
}
.my-class {
  font-weight: bold;
}
#unique-id {
  text-align: center;
}
h1,
p {
  line-height: 1.5;
}
```

### 2.2 Attribute Selectors

- `[attr]`: Targets elements with an attribute.
- `[attr="value"]`: Exact match.
- `[attr^="value"]`: Starts with value.
- `[attr$="value"]`: Ends with value.

### Example

```css
input[type="text"] {
  border: 1px solid black;
}
a[target="_blank"] {
  color: blue;
}
```

### 2.3 Pseudo-Classes

- `:hover`: Applies styles when hovered.
- `:nth-child(n)`: Targets nth child.
- `:first-child`: Targets first child.

### Example

```css
a:hover {
  text-decoration: underline;
}
li:nth-child(2) {
  color: green;
}
```

### 2.4 Pseudo-Elements

- `::before`: Inserts content before an element.
- `::after`: Inserts content after an element.

### Example

```css
p::before {
  content: "Note: ";
  font-weight: bold;
}
```

## 3. Specificity and Inheritance

### Specificity

- Inline Styles > IDs > Classes > Type Selectors > Universal

### Example

```css
p {
  color: blue;
}
p.special {
  color: green;
} /* More specific */
```

### Inheritance

- Some properties (e.g., `color`, `font`) are inherited by child elements.

## 4. Best Practices

1. **Avoid Inline Styles:** Use external stylesheets.
2. **Use Classes Instead of IDs for Styling:** IDs have high specificity.
3. **Organize CSS:** Group related styles together.
4. **Keep It Modular:** Use separate files for large projects.
5. **Use Naming Conventions:** Follow BEM methodology (`.block__element--modifier`).

## 5. Points to Remember

- Use shorthand properties (e.g., `margin: 10px 5px`).
- Avoid overusing `!important`.
- Keep selectors efficient and avoid deep nesting.

## 6. Additional Resources

- [CSS Selectors - MDN Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
- [CSS Specificity - CSS Tricks](https://css-tricks.com/specifics-on-css-specificity/)
