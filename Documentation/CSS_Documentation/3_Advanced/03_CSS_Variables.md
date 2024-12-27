# CSS Variables (Custom Properties)

## Basic Syntax

```css
:root {
  --primary-color: #007bff;
  --spacing-unit: 1rem;
  --border-style: 2px solid var(--primary-color);
}

.element {
  color: var(--primary-color);
  margin: var(--spacing-unit);
  border: var(--border-style);
}
```

## Variable Scoping

```css
/* Global Scope */
:root {
  --global-color: blue;
}

/* Component Scope */
.component {
  --local-color: red;
  color: var(--local-color);
}

/* Media Query Scope */
@media (prefers-color-scheme: dark) {
  :root {
    --global-color: #ffffff;
  }
}
```

## Dynamic Values

```css
.dynamic-element {
    --x-position: 0;
    --scale: 1;

    transform:
        translateX(calc(var(--x-position) * 1px))
        scale(var(--scale));
}

/* JavaScript Integration */
const element = document.querySelector('.dynamic-element');
element.style.setProperty('--x-position', '100');
```

## Fallback Values

```css
.element {
  /* Simple fallback */
  color: var(--undefined-color, blue);

  /* Nested fallbacks */
  margin: var(--spacing, var(--fallback-spacing, 1rem));

  /* Calc with fallback */
  width: calc(var(--width, 100%) - 20px);
}
```

## Complex Variables

```css
:root {
  /* Color System */
  --hue: 220;
  --saturation: 50%;
  --lightness: 50%;

  /* Computed Colors */
  --primary: hsl(var(--hue), var(--saturation), var(--lightness));
  --primary-light: hsl(
    var(--hue),
    var(--saturation),
    calc(var(--lightness) + 20%)
  );
  --primary-dark: hsl(
    var(--hue),
    var(--saturation),
    calc(var(--lightness) - 20%)
  );

  /* Spacing System */
  --spacing-base: 1rem;
  --spacing-xs: calc(var(--spacing-base) * 0.25);
  --spacing-sm: calc(var(--spacing-base) * 0.5);
  --spacing-lg: calc(var(--spacing-base) * 2);
  --spacing-xl: calc(var(--spacing-base) * 4);
}
```

## Theming System

```css
/* Light Theme */
[data-theme="light"] {
  --bg-primary: #ffffff;
  --bg-secondary: #f8f9fa;
  --text-primary: #212529;
  --text-secondary: #6c757d;
}

/* Dark Theme */
[data-theme="dark"] {
  --bg-primary: #212529;
  --bg-secondary: #343a40;
  --text-primary: #f8f9fa;
  --text-secondary: #adb5bd;
}

/* Theme Usage */
.card {
  background: var(--bg-primary);
  color: var(--text-primary);
  border: 1px solid var(--text-secondary);
}
```

## Responsive Variables

```css
:root {
  /* Base values */
  --header-height: 60px;
  --content-width: 1200px;
  --font-size: 16px;

  /* Responsive adjustments */
  @media (max-width: 768px) {
    --header-height: 50px;
    --content-width: 100%;
    --font-size: 14px;
  }

  @media (max-width: 480px) {
    --header-height: 40px;
    --font-size: 12px;
  }
}
```

## Component Architecture

```css
.component {
  /* Component variables */
  --component-spacing: 1rem;
  --component-bg: var(--bg-primary, white);
  --component-color: var(--text-primary, black);

  /* Private variables */
  --_internal-radius: 4px;
  --_internal-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);

  /* Usage */
  padding: var(--component-spacing);
  background: var(--component-bg);
  color: var(--component-color);
  border-radius: var(--_internal-radius);
  box-shadow: var(--_internal-shadow);
}
```

## Performance Best Practices

```css
/* Good - Limited scope */
.component {
  --local-var: blue;
}

/* Avoid - Global scope when unnecessary */
:root {
  --should-be-local: blue;
}

/* Good - Computed once */
:root {
  --computed-color: rgb(var(--r), var(--g), var(--b));
}

/* Avoid - Computed every time */
.element {
  color: rgb(var(--r), var(--g), var(--b));
}
```

## Animation with Variables

```css
.animated-element {
  --start-position: -100%;
  --end-position: 0%;

  @keyframes slide-in {
    from {
      transform: translateX(var(--start-position));
    }
    to {
      transform: translateX(var(--end-position));
    }
  }

  animation: slide-in 0.3s ease-out forwards;
}
```

## CSS Variables with JavaScript

```javascript
// Setting variables
document.documentElement.style.setProperty("--primary-color", "#ff0000");

// Getting variables
const styles = getComputedStyle(document.documentElement);
const value = styles.getPropertyValue("--primary-color").trim();

// Dynamic updates
window.addEventListener("resize", () => {
  const width = window.innerWidth;
  document.documentElement.style.setProperty("--viewport-width", `${width}px`);
});
```

## Best Practices

1. Naming Conventions

   - Use meaningful, descriptive names
   - Follow a consistent pattern
   - Prefix private variables with `_`
   - Use kebab-case

2. Organization

   - Group related variables
   - Keep global variables minimal
   - Use local scope when possible
   - Document complex variables

3. Performance

   - Minimize recalculations
   - Avoid deep variable nesting
   - Use local scope for frequent updates
   - Cache computed values

4. Maintainability

   - Create a single source of truth
   - Use semantic naming
   - Document variable relationships
   - Keep fallbacks reasonable

5. Browser Support
   - Provide fallbacks for older browsers
   - Test cross-browser compatibility
   - Use feature detection when needed
