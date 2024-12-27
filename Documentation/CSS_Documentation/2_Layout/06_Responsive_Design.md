# Comprehensive CSS Responsive Design Guide

## Core Concepts

### Media Query Fundamentals

```css
/* Basic Structure */
@media [media-type] ([media-feature]) {
  /* CSS rules */
}

/* Common Media Types */
@media screen {
  /* For screens */
}
@media print {
  /* For printing */
}
@media all {
  /* Default, for all devices */
}

/* Logical Operators */
@media screen and (min-width: 768px) {
  /* AND operator */
}
@media screen or (min-width: 768px) {
  /* OR operator */
}
@media not screen {
  /* NOT operator */
}

/* Range Queries */
@media (width >= 768px) {
  /* Modern syntax */
}
@media (768px <= width <= 1200px) {
  /* Range */
}
```

### Standard Breakpoints System

```css
/* Mobile-First Approach */
:root {
  --breakpoint-sm: 576px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 992px;
  --breakpoint-xl: 1200px;
  --breakpoint-xxl: 1400px;
}

/* Mixins (Using SCSS) */
@mixin respond-above($breakpoint) {
  @media (min-width: $breakpoint) {
    @content;
  }
}

/* Usage Example */
.element {
  /* Mobile base styles */
  padding: 1rem;

  /* Tablet and above */
  @media (min-width: 768px) {
    padding: 2rem;
  }

  /* Desktop and above */
  @media (min-width: 1200px) {
    padding: 3rem;
  }
}
```

## Advanced Responsive Properties

### Fluid Units Guide

```css
/* Viewport Units */
.fluid-element {
  /* Viewport Width */
  width: 50vw; /* 50% of viewport width */

  /* Viewport Height */
  height: 75vh; /* 75% of viewport height */

  /* Dynamic Minimum */
  width: vmin; /* Smaller of vw or vh */

  /* Dynamic Maximum */
  height: vmax; /* Larger of vw or vh */

  /* New Viewport Units */
  width: lvw; /* Largest viewport width */
  height: svh; /* Small viewport height */
  margin: dvw; /* Dynamic viewport width */
}

/* Modern CSS Functions */
.modern-fluid {
  /* Clamp: (min, preferred, max) */
  width: clamp(300px, 50vw, 800px);

  /* Min: Smallest value wins */
  padding: min(5vw, 50px);

  /* Max: Largest value wins */
  margin: max(2vw, 20px);
}
```

### Typography System

```css
:root {
  /* Base Sizes */
  --font-size-base: 1rem;
  --scale-ratio: 1.25;

  /* Fluid Type Scale */
  --h1: clamp(2rem, 5vw + 1rem, 4rem);
  --h2: clamp(1.8rem, 4vw + 1rem, 3.5rem);
  --h3: clamp(1.6rem, 3vw + 1rem, 3rem);
  --body: clamp(1rem, 1vw + 0.75rem, 1.25rem);
}

/* Implementation */
body {
  font-size: var(--body);
  line-height: calc(2px + 2ex + 2px); /* Fluid line height */
}

h1 {
  font-size: var(--h1);
  /* Fluid margin based on font size */
  margin-bottom: calc(1em + 0.5vw);
}
```

## Responsive Container Patterns

### Modern Container Queries

```css
/* Define containment context */
.card-container {
  container-type: inline-size;
  container-name: card;
}

/* Style based on container size */
@container card (min-width: 400px) {
  .card {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: clamp(1rem, 3cqi, 2rem);
  }
}

/* Container Query Units */
.element {
  padding: 2cqi; /* Relative to inline container size */
  margin: 2cqb; /* Relative to block container size */
}
```

### Fluid Image Patterns

```css
/* Modern Image Handling */
.responsive-image {
    /* Basic Responsive Image */
    max-width: 100%;
    height: auto;

    /* Maintain Aspect Ratio */
    aspect-ratio: 16/9;
    object-fit: cover;

    /* Prevent Layout Shift */
    content-visibility: auto;
    contain: size layout;
}

/* Art Direction Pattern */
<picture>
    <!-- Desktop Image -->
    <source
        media="(min-width: 1200px)"
        srcset="large.webp 1200w,
                medium.webp 800w"
        sizes="80vw">

    <!-- Tablet Image -->
    <source
        media="(min-width: 768px)"
        srcset="medium.webp 800w,
                small.webp 400w"
        sizes="90vw">

    <!-- Default/Mobile Image -->
    <img
        src="small.webp"
        alt="Description"
        loading="lazy"
        decoding="async"
        width="400"
        height="300">
</picture>
```

### Modern Grid Layouts

```css
/* Auto-Fit Grid */
.grid {
  --min-column: 250px;

  display: grid;
  grid-template-columns: repeat(
    auto-fit,
    minmax(min(100%, var(--min-column)), 1fr)
  );
  gap: clamp(1rem, 3vw, 2rem);
}

/* Responsive Grid Areas */
.layout {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  grid-template-columns: minmax(200px, 1fr) 3fr;

  @media (max-width: 768px) {
    grid-template-areas:
      "header"
      "main"
      "sidebar"
      "footer";
    grid-template-columns: 1fr;
  }
}
```

## Performance Optimization

### Loading Strategies

```html
<!-- Preload Critical Resources -->
<link
  rel="preload"
  href="critical-font.woff2"
  as="font"
  type="font/woff2"
  crossorigin
/>

<!-- Lazy Load Images -->
<img
  loading="lazy"
  decoding="async"
  src="image.webp"
  srcset="small.webp 300w, medium.webp 600w, large.webp 900w"
  sizes="(max-width: 768px) 100vw,
           (max-width: 1200px) 50vw,
           33vw"
  alt="Description"
/>
```

### Critical CSS Pattern

```html
<head>
  <!-- Inline Critical CSS -->
  <style>
    /* Above-the-fold styles */
    .hero {
      min-height: 100vh;
      display: grid;
      place-items: center;
    }
  </style>

  <!-- Defer Non-Critical CSS -->
  <link
    rel="preload"
    href="styles.css"
    as="style"
    onload="this.onload=null;this.rel='stylesheet'"
  />
</head>
```

## Best Practices Checklist

### Development Workflow

1. Start Mobile-First

   - Base styles for smallest viewport
   - Progressive enhancement with media queries
   - Test on real devices

2. Use Flexible Units

   - Prefer relative units (rem, em, %)
   - Implement fluid type scales
   - Avoid fixed pixel values

3. Optimize Performance

   - Compress and convert images to WebP
   - Implement lazy loading
   - Use content-visibility for off-screen content

4. Maintain Consistency

   - Define global CSS custom properties
   - Create reusable components
   - Document breakpoints and patterns

5. Test Thoroughly
   - Cross-browser testing
   - Device testing
   - Accessibility validation

## Global Setup

### CSS Reset

```css
/* Modern CSS Reset */
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  /* Base font-size for rem calculations */
  font-size: 62.5%; /* Makes 1rem = 10px */
}

body {
  /* Prevent layout shifts */
  min-height: 100vh;
  text-rendering: optimizeSpeed;
  line-height: 1.5;
}
```

### Responsive Units System

```css
:root {
  /* Spacing System */
  --space-unit: 1rem;
  --space-xs: calc(0.25 * var(--space-unit));
  --space-sm: calc(0.5 * var(--space-unit));
  --space-md: calc(1 * var(--space-unit));
  --space-lg: calc(2 * var(--space-unit));
  --space-xl: calc(4 * var(--space-unit));

  /* Container Widths */
  --container-max-width: 120rem;
  --container-padding: 2rem;
}
```

## Fluid Typography Formula

```css
/* Fluid Typography */
:root {
  --min-font-size: 16;
  --max-font-size: 20;
  --min-viewport-width: 320;
  --max-viewport-width: 1200;

  --font-scale: calc(
    (var(--max-font-size) - var(--min-font-size)) / (var(--max-viewport-width) -
          var(--min-viewport-width))
  );

  --fluid-font-size: calc(
    var(--min-font-size) px + (100vw - var(--min-viewport-width) px) * var(--font-scale)
  );

  font-size: clamp(
    var(--min-font-size) px,
    var(--fluid-font-size),
    var(--max-font-size) px
  );
}
```

## Responsive Container System

```css
.container {
  --padding: max(
    var(--container-padding),
    calc((100vw - var(--container-max-width)) / 2)
  );

  width: min(100% - (var(--padding) * 2), var(--container-max-width));
  margin-inline: auto;
}

/* Fluid Padding */
.container {
  padding: clamp(1.5rem, 5vw, 3rem);
}
```

## Responsive Images

### Art Direction

```html
<picture>
  <source media="(min-width: 1200px)" srcset="large.jpg" sizes="100vw" />
  <source media="(min-width: 800px)" srcset="medium.jpg" sizes="100vw" />
  <img
    src="small.jpg"
    alt="Description"
    loading="lazy"
    width="800"
    height="600"
  />
</picture>
```

### CSS Image Solutions

```css
/* Maintain Aspect Ratio */
.image-wrapper {
  aspect-ratio: 16/9;
  position: relative;
}

.image-wrapper img {
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Background Images */
.responsive-bg {
  background-image: var(--mobile-image);
  background-size: cover;

  @media (min-width: 768px) {
    background-image: var(--desktop-image);
  }
}
```

## Flexible Layout Components

### Card Grid System

```css
.grid {
  --min-column-width: 25rem;

  display: grid;
  grid-template-columns: repeat(
    auto-fit,
    minmax(min(var(--min-column-width), 100%), 1fr)
  );
  gap: clamp(1rem, 3vw, 3rem);
}
```

### Responsive Flex Layout

```css
.flex-container {
  --gap: clamp(1rem, 2vw, 2rem);

  display: flex;
  flex-wrap: wrap;
  gap: var(--gap);
}

.flex-item {
  flex: 1 1 calc((var(--container-max-width) / 4) - var(--gap));
  min-width: min(100%, 30rem);
}
```

## Key Formulas to Remember

1. Fluid Property Calculation:

```css
property: calc(
  min-size + (max-size - min-size) * ((100vw - min-viewport) / (max-viewport -
            min-viewport))
);
```

2. Aspect Ratio Scaling:

```css
padding-bottom: calc(height / width * 100%);
```

3. Dynamic Spacing:

```css
margin: calc(1rem + 2vw);
```

## Best Practices Checklist

### Units Selection

- `rem` for typography and component sizing
- `em` for media queries and component internals
- `%` for layouts and flexible widths
- `vw/vh` for viewport-relative sizing
- `ch` for text container widths
- `px` only for borders and small decorative elements

### Layout Construction

1. Start with CSS Reset
2. Define Global Variables
3. Create Type Scale
4. Build Component Library
5. Implement Layout System
6. Add Responsive Refinements

### Component Architecture

```css
.component {
  /* Base styles */
  --component-spacing: clamp(1rem, 3vw, 2rem);

  /* Layout */
  display: flex;
  gap: var(--component-spacing);

  /* Responsive adjustments */
  @media (max-width: 768px) {
    flex-direction: column;
  }
}
```

### Performance Guidelines

1. Use `will-change` sparingly
2. Implement content-visibility
3. Lazy load off-screen content
4. Optimize images and assets
5. Use CSS containment

## Common Responsive Patterns

### Sidebar Layout

```css
.layout {
  --sidebar-width: min(30vw, 30rem);

  display: grid;
  grid-template-columns:
    minmax(var(--sidebar-width), 1fr)
    minmax(0, 2fr);

  @media (max-width: 768px) {
    grid-template-columns: 1fr;
  }
}
```

### Holy Grail Layout

```css
.holy-grail {
  display: grid;
  grid-template:
    "header header header" auto
    "left main right" 1fr
    "footer footer footer" auto
    / auto 1fr auto;

  @media (max-width: 768px) {
    grid-template:
      "header" auto
      "main" 1fr
      "left" auto
      "right" auto
      "footer" auto
      / 1fr;
  }
}
```
