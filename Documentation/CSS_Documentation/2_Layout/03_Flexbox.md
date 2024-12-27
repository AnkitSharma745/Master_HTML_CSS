# Flexbox in CSS

The Flexible Box Layout Module, or Flexbox, is a layout model that provides an efficient way to align and distribute space among items in a container, even if their sizes are dynamic.

---

## 1. Core Concepts

### Flex Container

- The parent element where Flexbox is applied.
- **Property**: `display: flex;`

### Flex Items

- Direct child elements of the Flex Container.

---

## 2. Properties of Flex Container

### a) Display

- Enables Flexbox: `display: flex;` or `display: inline-flex;`

### b) Flex Direction

- Defines the main axis.
- **Values**:
  - `row` (default): Left to right.
  - `row-reverse`: Right to left.
  - `column`: Top to bottom.
  - `column-reverse`: Bottom to top.
- **Property**: `flex-direction`

### c) Justify Content

- Aligns items along the main axis.
- **Values**:
  - `flex-start` (default): Aligns items at the start.
  - `flex-end`: Aligns items at the end.
  - `center`: Centers items.
  - `space-between`: Distributes items with space between.
  - `space-around`: Adds space around items.
  - `space-evenly`: Equal spacing.
- **Property**: `justify-content`

### d) Align Items

- Aligns items along the cross axis.
- **Values**:
  - `stretch` (default): Stretches items.
  - `flex-start`: Aligns items at the start.
  - `flex-end`: Aligns items at the end.
  - `center`: Centers items.
  - `baseline`: Aligns items to the text baseline.
- **Property**: `align-items`

### e) Align Content

- Aligns multi-line content in the cross axis.
- **Values**:
  - Same as `justify-content` but for multi-line layouts.
- **Property**: `align-content`

### f) Flex Wrap

- Controls whether items wrap onto the next line.
- **Values**:
  - `nowrap` (default): Single line.
  - `wrap`: Multiple lines.
  - `wrap-reverse`: Reverses wrapping direction.
- **Property**: `flex-wrap`

### g) Gap

- Controls spacing between items.
- **Property**: `gap`, `row-gap`, `column-gap`

---

## 3. Properties of Flex Items

### a) Order

- Changes the visual order of items.
- **Property**: `order`

### b) Flex Grow

- Defines how much a flex item can grow.
- **Property**: `flex-grow`

### c) Flex Shrink

- Defines how much a flex item can shrink.
- **Property**: `flex-shrink`

### d) Flex Basis

- Specifies the initial size of an item.
- **Property**: `flex-basis`

### e) Align Self

- Overrides `align-items` for an individual item.
- **Property**: `align-self`

---

## 4. Example

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 10px;
}

.item {
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 100px;
}
```

---

## 5. Points to Remember

1. **Use Cases**:

   - Navigation bars, responsive layouts, alignment of items.

2. **Best Practices**:

   - Avoid setting fixed widths when using `flex-grow` or `flex-shrink`.
   - Use `gap` instead of margins for spacing.

3. **Industry Tip**:
   - Use browser dev tools to visualize Flexbox layouts.

---

## 6. Additional Resources

- [MDN Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [CSS Tricks Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
