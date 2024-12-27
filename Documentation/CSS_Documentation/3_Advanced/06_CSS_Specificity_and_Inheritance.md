# CSS Specificity and Inheritance

## Specificity Hierarchy

### Specificity Values

```css
/* Specificity: 1-0-0 */
#unique-id {
}

/* Specificity: 0-1-0 */
.class-name {
}
[attribute] {
}
:pseudo-class {
}

/* Specificity: 0-0-1 */
element {
}
::pseudo-element {
}

/* Specificity: 0-0-0 */
* {
} /* Universal selector */
```

### Calculating Specificity

```css
/* Examples with specificity scores */

/* Specificity: 1-0-0 (100) */
#header {
}

/* Specificity: 0-2-0 (020) */
.navigation.dropdown {
}

/* Specificity: 0-1-1 (011) */
nav.menu {
}

/* Specificity: 0-1-2 (012) */
div.container p {
}

/* Specificity: 1-2-1 (121) */
#content .widget.sidebar h2 {
}
```

## Inheritance

### Inheritable Properties

```css
/* Properties that inherit by default */
.parent {
  color: blue; /* Inherits */
  font-family: Arial; /* Inherits */
  font-size: 16px; /* Inherits */
  line-height: 1.5; /* Inherits */
  text-align: center; /* Inherits */
  cursor: pointer; /* Inherits */
}

/* Properties that don't inherit by default */
.parent {
  border: 1px solid black; /* Doesn't inherit */
  padding: 20px; /* Doesn't inherit */
  margin: 10px; /* Doesn't inherit */
  background: #f0f0f0; /* Doesn't inherit */
}
```

### Controlling Inheritance

```css
.element {
  /* Force inheritance */
  border: inherit;
  margin: inherit;
  padding: inherit;

  /* Prevent inheritance */
  color: initial;
  font-size: initial;

  /* Reset to browser default */
  all: initial;

  /* Inherit everything */
  all: inherit;

  /* Unset (inheritance if inheritable, initial if not) */
  all: unset;

  /* Explicitly use cascaded value */
  all: revert;
}
```

## Cascade Order

### Priority Levels

```css
/* Highest to Lowest Priority */

/* 1. !important declarations */
.override {
  color: red !important;
}

/* 2. Inline styles */
<div style="color: blue;">

/* 3. ID selectors */
#header {
}

/* 4. Class selectors, attributes, and pseudo-classes */
.navigation {
}
[type="text"] {
}
:hover {
}

/* 5. Element selectors and pseudo-elements */
div {
}
::before {
}

/* 6. Universal selector */
* {
}
```

## Specificity Best Practices

### BEM Naming Convention

```css
/* Block */
.block {
}

/* Element */
.block__element {
}

/* Modifier */
.block--modifier {
}
.block__element--modifier {
}

/* Example */
.card {
}
.card__title {
}
.card__image {
}
.card--featured {
}
```

### Managing Specificity

```css
/* Good - Low specificity */
.message {
}
.message.error {
}

/* Avoid - High specificity */
div.container .sidebar div.message {
}

/* Better - Flatten selectors */
.container-message {
}
.sidebar-message {
}

/* Using data attributes for variants */
.button[data-size="large"] {
}
.button[data-theme="dark"] {
}
```

## Common Patterns and Solutions

### Specificity Wars

```css
/* Problem - Specificity conflicts */
#sidebar .widget h2 {
} /* High specificity */
.widget-title {
} /* Lower specificity */

/* Solution - Use classes */
.widget-title {
}
.widget-title--sidebar {
}
```

### Inheritance Control

```css
/* Reset inherited styles */
.component {
  font: inherit;
  color: inherit;
  /* Reset other inherited properties */
}

/* Force specific inheritance */
.text-inherit {
  color: inherit !important;
}
```

## Debugging Specificity

### Specificity Debugging Tools

```css
/* Add visual debugging */
[style] {
  outline: 2px dotted red !important;
}
[id] {
  outline: 2px dotted blue !important;
}
[class] {
  outline: 2px dotted green !important;
}
```

## Best Practices

1. Specificity Guidelines

   - Keep specificity as low as possible
   - Avoid ID selectors for styling
   - Use classes as primary selectors
   - Avoid !important
   - Use specific selectors only when necessary

2. Inheritance Management

   - Understand which properties inherit
   - Use inheritance intentionally
   - Reset inherited values when needed
   - Document inheritance dependencies

3. Selector Strategy

   - Use BEM or similar methodology
   - Keep selectors flat
   - Avoid deep nesting
   - Use meaningful class names
   - Document complex selectors

4. Performance Considerations

   - Minimize selector complexity
   - Avoid universal selectors
   - Use direct child selectors when possible
   - Optimize selector matching

5. Maintainability
   - Document specificity decisions
   - Use consistent naming conventions
   - Create style guide documentation
   - Regular specificity audits

## Troubleshooting Guide

### Common Issues

```css
/* Issue: Styles not applying */
/* Check specificity hierarchy */
/* Use browser dev tools to inspect */

/* Issue: Inheritance problems */
/* Verify property inheritance */
/* Check for unintended reset */

/* Issue: Specificity conflicts */
/* Refactor to use classes */
/* Remove unnecessary specificity */
```

### Quick Fixes

```css
/* Temporary specificity boost */
.class.class {
}

/* Reset inheritance chain */
.element {
  all: initial;
  /* Add back desired styles */
}

/* Isolate styles */
.element:where(.element) {
}
```
