# CSS Icons and Fonts: Complete Guide

## Table of Contents

- [Icon Implementation](#icon-implementation)
- [Web Fonts](#web-fonts)
- [Typography](#typography)
- [Font Properties](#font-properties)
- [Icon Animation](#icon-animation)
- [Performance Optimization](#performance-optimization)
- [Best Practices](#best-practices)
- [Accessibility](#accessibility)

## Icon Implementation

### Icon Fonts

```css
/* Using Icon Fonts (e.g., Font Awesome) */
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css");

.icon {
  font-family: "Font Awesome 6 Free";
  font-weight: 900;
}

/* Sizing icons */
.icon-sm {
  font-size: 1rem;
}
.icon-md {
  font-size: 1.5rem;
}
.icon-lg {
  font-size: 2rem;
}

/* Coloring icons */
.icon-primary {
  color: #007bff;
}
.icon-secondary {
  color: #6c757d;
}
```

### SVG Icons

```css
/* SVG icon styles */
.svg-icon {
  width: 24px;
  height: 24px;
  fill: currentColor;
}

/* SVG icon sizes */
.svg-icon-sm {
  width: 16px;
  height: 16px;
}

.svg-icon-lg {
  width: 32px;
  height: 32px;
}

/* SVG sprite usage */
.icon-sprite {
  display: inline-block;
  width: 24px;
  height: 24px;
  background-image: url("sprite.svg");
  background-repeat: no-repeat;
}
```

### CSS Icons

```css
/* Pure CSS icons */
.arrow-right {
  width: 0;
  height: 0;
  border-top: 6px solid transparent;
  border-bottom: 6px solid transparent;
  border-left: 10px solid #000;
}

.close-icon {
  position: relative;
  width: 20px;
  height: 20px;
}

.close-icon::before,
.close-icon::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 2px;
  background: #000;
  transform: rotate(45deg);
  top: 50%;
}

.close-icon::after {
  transform: rotate(-45deg);
}
```

## Web Fonts

### Font Face Declaration

```css
/* Basic @font-face */
@font-face {
  font-family: "CustomFont";
  src: url("custom-font.woff2") format("woff2"), url("custom-font.woff") format("woff");
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}

/* Variable font */
@font-face {
  font-family: "VariableFont";
  src: url("variable-font.woff2") format("woff2-variations");
  font-weight: 100 900;
  font-stretch: 75% 125%;
  font-style: normal;
}
```

### Google Fonts Implementation

```css
/* Google Fonts import */
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap");

/* Font usage */
body {
  font-family: "Roboto", sans-serif;
}

/* Font variants */
.light {
  font-weight: 300;
}
.regular {
  font-weight: 400;
}
.medium {
  font-weight: 500;
}
.bold {
  font-weight: 700;
}
```

## Typography

### Text Properties

```css
.text-styling {
  /* Basic properties */
  font-size: 16px;
  line-height: 1.5;
  letter-spacing: 0.5px;
  word-spacing: 2px;

  /* Advanced properties */
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  /* Hanging punctuation */
  hanging-punctuation: first;
}

/* Font feature settings */
.advanced-typography {
  font-feature-settings: "liga" 1, /* Ligatures */ "kern" 1,
    /* Kerning */ "dlig" 1, /* Discretionary ligatures */ "ss01" 1; /* Stylistic set 1 */
}
```

### Responsive Typography

```css
/* Fluid typography */
:root {
  --fluid-min-width: 320;
  --fluid-max-width: 1200;
  --fluid-min-size: 16;
  --fluid-max-size: 24;
  --fluid-min-scale: 1.2;
  --fluid-max-scale: 1.333;
}

body {
  font-size: clamp(
    var(--fluid-min-size) px,
    calc(
      1rem + ((1vw - var(--fluid-min-width) px/100) * var(--fluid-max-size))
    ),
    var(--fluid-max-size) px
  );
}

/* Modular scale */
h1 {
  font-size: calc(var(--base-size) * var(--scale-ratio) * var(--scale-ratio));
}
h2 {
  font-size: calc(var(--base-size) * var(--scale-ratio));
}
```

## Font Properties

### Advanced Font Controls

```css
.font-controls {
  /* Font variations */
  font-variation-settings: "wght" 400, "wdth" 100, "slnt" 0;

  /* Font optical sizing */
  font-optical-sizing: auto;

  /* Font stretch */
  font-stretch: 125%;

  /* Font synthesis */
  font-synthesis: none;
}

/* Variable font animations */
@keyframes weight-change {
  from {
    font-variation-settings: "wght" 100;
  }
  to {
    font-variation-settings: "wght" 900;
  }
}
```

### Text Decoration

```css
.text-decoration {
  /* Basic decoration */
  text-decoration: underline;
  text-decoration-color: #ff0000;
  text-decoration-thickness: 2px;
  text-decoration-style: wavy;

  /* Text underline offset */
  text-underline-offset: 0.2em;

  /* Text emphasis */
  text-emphasis: filled circle;
  text-emphasis-position: over right;
}
```

## Icon Animation

### Animated Icons

```css
/* Rotating icon */
.icon-spin {
  animation: spin 2s linear infinite;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

/* Pulse effect */
.icon-pulse {
  animation: pulse 1s ease-in-out infinite;
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}
```

### Interactive Icons

```css
.icon-interactive {
  transition: all 0.3s ease;
}

.icon-interactive:hover {
  transform: translateY(-2px);
  color: #007bff;
}

/* Icon state changes */
.icon-state {
  position: relative;
}

.icon-state::after {
  content: "";
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 100%;
  height: 2px;
  background: currentColor;
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.icon-state:hover::after {
  transform: scaleX(1);
}
```

## Performance Optimization

### Font Loading Strategies

```css
/* Font display options */
@font-face {
  font-family: "Performance";
  src: url("font.woff2") format("woff2");
  font-display: optional;
}

/* Font subsetting */
@font-face {
  font-family: "Subset";
  src: url("subset-latin.woff2") format("woff2");
  unicode-range: U+0000-00FF;
}

/* System font stack */
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
}
```

### Icon Loading

```css
/* Icon font preload */
<link rel="preload" 
      href="icon-font.woff2" 
      as="font" 
      type="font/woff2" 
      crossorigin>

/* SVG optimization */
.optimized-svg {
  background-image: url("data:image/svg+xml,%3Csvg...");
}
```

## Best Practices

1. **Font Loading**

```css
/* FOIT prevention */
.no-foit {
  font-display: swap;
}

/* Font loading phases */
.font-loading {
  .phase-1 {
    font-family: system-ui;
  }
  .phase-2 {
    font-family: "Custom Font", system-ui;
  }
}
```

2. **Icon Usage**

```css
/* Semantic icon usage */
.icon-button {
  display: inline-flex;
  align-items: center;
  gap: 0.5em;
}

/* Icon sizing relative to text */
.icon-relative {
  font-size: 1em;
  vertical-align: middle;
}
```

## Accessibility

### Icon Accessibility

```css
/* Screen reader text */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}

/* Accessible icon buttons */
.icon-button {
  position: relative;
  padding: 0.5em;
  background: none;
  border: none;
  cursor: pointer;
}

/* Focus styles */
.icon-button:focus {
  outline: 2px solid #007bff;
  outline-offset: 2px;
}
```
