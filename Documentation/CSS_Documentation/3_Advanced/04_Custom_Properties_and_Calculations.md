# CSS Custom Properties and Calculations

## CSS Calc() Function

### Basic Calculations

```css
:root {
  --base-spacing: 20px;
}

.element {
  /* Basic arithmetic */
  width: calc(100% - 20px);
  height: calc(100vh - var(--base-spacing));
  padding: calc(var(--base-spacing) / 2);
  margin: calc(var(--base-spacing) * 1.5);

  /* Mixed units */
  top: calc(50% + 20px);
  left: calc(100vw - 100%);

  /* Nested calculations */
  font-size: calc(16px + calc(2 * 0.5rem));
}
```

### Advanced Calculations

```css
.advanced-calc {
  /* Multiple operations */
  width: calc(100% - (2 * var(--spacing)) - (2 * var(--border-width)));

  /* Complex expressions */
  transform: calc(1rem * (1 + var(--scale-factor)));

  /* Viewport-relative calculations */
  margin: calc((100vw - var(--content-width)) / 2);

  /* Aspect ratio calculations */
  padding-bottom: calc(100% * (9 / 16));
}
```

## Modern Math Functions

### min(), max(), and clamp()

```css
.modern-math {
  /* min() for responsive values */
  width: min(1200px, 100% - 2rem);

  /* max() for minimum sizes */
  font-size: max(12px, 1.5vw);

  /* clamp() for fluid values */
  padding: clamp(1rem, 5vw, 3rem);
  font-size: clamp(1rem, 1rem + 2vw, 2rem);

  /* Combined functions */
  width: min(max(300px, 50%), 1200px);
}
```

### Complex Calculations

```css
:root {
  /* Spacing system */
  --ratio: 1.5;
  --s0: 1rem;
  --s1: calc(var(--s0) * var(--ratio));
  --s2: calc(var(--s1) * var(--ratio));
  --s3: calc(var(--s2) * var(--ratio));

  /* Dynamic spacing */
  --fluid-space: calc(1rem + 0.5vw);

  /* Responsive type scale */
  --min-width: 320;
  --max-width: 1200;
  --min-font: 16;
  --max-font: 24;

  --slope: calc(
    (var(--max-font) - var(--min-font)) / (var(--max-width) - var(--min-width))
  );

  --fluid-font-size: calc(
    var(--min-font) px + (100vw - var(--min-width) px) * var(--slope)
  );
}
```

## Custom Properties Patterns

### Component-Based Properties

```css
.component {
  /* Base properties */
  --component-spacing: 1rem;
  --component-color: #007bff;

  /* Computed properties */
  --_internal-padding: calc(var(--component-spacing) * 1.5);
  --_internal-margin: calc(var(--component-spacing) / 2);

  /* Property usage */
  padding: var(--_internal-padding);
  margin: var(--_internal-margin);
  color: var(--component-color);
}
```

### State-Based Properties

```css
.button {
  /* Default state */
  --button-bg: #007bff;
  --button-color: white;
  --button-scale: 1;

  /* Property application */
  background: var(--button-bg);
  color: var(--button-color);
  transform: scale(var(--button-scale));
  transition: transform 0.2s;
}

.button:hover {
  --button-scale: 1.05;
}

.button:active {
  --button-scale: 0.95;
}

.button[disabled] {
  --button-bg: #6c757d;
}
```

## Advanced Layout Techniques

### Dynamic Grid System

```css
.grid {
  --columns: 3;
  --gap: 1rem;
  --min-col-width: 250px;

  display: grid;
  gap: var(--gap);
  grid-template-columns: repeat(
    auto-fit,
    minmax(min(100%, max(var(--min-col-width), 100% / var(--columns))), 1fr)
  );
}
```

### Fluid Typography System

```css
:root {
  /* Type scale ratio */
  --ratio: 1.25;

  /* Base sizes */
  --text-xs: calc(var(--text-base) / var(--ratio));
  --text-sm: calc(var(--text-base) / sqrt(var(--ratio)));
  --text-base: clamp(1rem, 1vw + 0.75rem, 1.25rem);
  --text-lg: calc(var(--text-base) * sqrt(var(--ratio)));
  --text-xl: calc(var(--text-base) * var(--ratio));
  --text-2xl: calc(var(--text-xl) * var(--ratio));
  --text-3xl: calc(var(--text-2xl) * var(--ratio));
}
```

## Performance Optimization

### Efficient Property Usage

```css
/* Good - Computed once */
:root {
  --complex-calculation: calc(100vw - (2 * var(--spacing)));
}

.element {
  width: var(--complex-calculation);
}

/* Avoid - Computed for each element */
.element {
  width: calc(100vw - (2 * var(--spacing)));
}
```

### Responsive Optimizations

```css
:root {
  /* Base values */
  --desktop-spacing: 2rem;
  --mobile-spacing: 1rem;

  /* Responsive property */
  --responsive-spacing: clamp(
    var(--mobile-spacing),
    calc(0.5rem + 2vw),
    var(--desktop-spacing)
  );
}
```

## Best Practices

1. Calculation Guidelines

   - Keep calculations simple and readable
   - Use meaningful variable names
   - Avoid deep nesting of calc()
   - Cache complex calculations in variables

2. Property Naming

   - Use descriptive, semantic names
   - Follow consistent naming patterns
   - Prefix private properties with '\_'
   - Group related properties

3. Performance Considerations

   - Minimize recalculations
   - Use local scope when possible
   - Cache computed values
   - Avoid unnecessary complexity

4. Maintainability

   - Document complex calculations
   - Use comments for clarity
   - Create a single source of truth
   - Keep fallbacks reasonable

5. Debug Strategies

```css
/* Debug outline */
* {
  outline: 1px solid var(--debug-color, red);
}

/* Variable inspector */
:root {
  --debug: true;
}

.debug-info::after {
  content: "width: " var(--width) "\A""height: " var(--height);
  white-space: pre;
  display: var(--debug, none);
}
```
