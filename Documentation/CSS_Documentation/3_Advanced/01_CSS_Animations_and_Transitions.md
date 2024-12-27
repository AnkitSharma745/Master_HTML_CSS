# CSS Animations and Transitions

## Transitions

### Basic Syntax

```css
.element {
  transition: property duration timing-function delay;
}
```

### Transition Properties

```css
.element {
  /* Single property */
  transition: transform 0.3s ease-in-out;

  /* Multiple properties */
  transition: transform 0.3s ease-in-out, opacity 0.2s linear;

  /* All properties */
  transition: all 0.3s ease-in-out;
}
```

### Timing Functions

```css
.element {
  /* Common Functions */
  transition-timing-function: linear;
  transition-timing-function: ease;
  transition-timing-function: ease-in;
  transition-timing-function: ease-out;
  transition-timing-function: ease-in-out;

  /* Custom Cubic Bezier */
  transition-timing-function: cubic-bezier(0.68, -0.55, 0.265, 1.55);

  /* Steps */
  transition-timing-function: steps(4, end);
}
```

## Animations

### Keyframes Syntax

```css
@keyframes animationName {
  from {
    /* styles */
  }
  to {
    /* styles */
  }
}

/* Or with percentages */
@keyframes animationName {
  0% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(100px);
  }
  100% {
    transform: translateX(0);
  }
}
```

### Animation Properties

```css
.element {
  animation: name duration timing-function delay iteration-count direction
    fill-mode play-state;

  /* Individual Properties */
  animation-name: animationName;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: 0.5s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
  animation-fill-mode: forwards;
  animation-play-state: running;
}
```

## Performance Optimization

### Hardware Acceleration

```css
.optimized-animation {
  /* Promote to GPU */
  transform: translateZ(0);
  will-change: transform;

  /* Composite properties */
  transform: translate3d(0, 0, 0);
  backface-visibility: hidden;
}
```

### Performance Best Practices

```css
/* Prefer opacity & transform */
.good-performance {
  transform: translateX(100px);
  opacity: 0.5;
}

/* Avoid animating layout properties */
.poor-performance {
  width: 100px; /* Triggers layout */
  height: 100px; /* Triggers layout */
  top: 50px; /* Triggers layout */
}
```

## Common Animation Patterns

### Fade In

```css
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.fade-in {
  animation: fadeIn 0.3s ease-in forwards;
}
```

### Slide In

```css
@keyframes slideIn {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0);
  }
}

.slide-in {
  animation: slideIn 0.5s ease-out forwards;
}
```

### Bounce

```css
@keyframes bounce {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

.bounce {
  animation: bounce 1s ease-in-out infinite;
}
```

### Pulse

```css
@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.05);
  }
  100% {
    transform: scale(1);
  }
}

.pulse {
  animation: pulse 2s ease-in-out infinite;
}
```

## Advanced Techniques

### Scroll-Triggered Animations

```css
.reveal {
  opacity: 0;
  transform: translateY(20px);
  transition: 0.5s all ease-in-out;
}

.reveal.active {
  opacity: 1;
  transform: translateY(0);
}
```

### State-Based Animations

```css
.button {
  transition: all 0.3s ease;
}

.button:hover {
  transform: scale(1.1);
}

.button:active {
  transform: scale(0.95);
}
```

### Sequenced Animations

```css
.container > * {
  opacity: 0;
  animation: fadeIn 0.5s ease-out forwards;
}

.container > *:nth-child(1) {
  animation-delay: 0.1s;
}
.container > *:nth-child(2) {
  animation-delay: 0.2s;
}
.container > *:nth-child(3) {
  animation-delay: 0.3s;
}
```

## Accessibility Considerations

```css
/* Respect user preferences */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

## Best Practices

1. Performance

   - Use `transform` and `opacity` for animations
   - Avoid animating layout properties
   - Use `will-change` sparingly
   - Implement hardware acceleration when needed

2. Timing

   - Keep animations under 1 second
   - Use appropriate easing
   - Add delays for sequenced animations
   - Consider animation purpose when setting duration

3. User Experience

   - Don't animate everything
   - Make animations meaningful
   - Provide reduced motion alternatives
   - Test on different devices

4. Code Organization

   - Name animations semantically
   - Group related animations
   - Use CSS custom properties for values
   - Comment complex animations

5. Browser Support

   - Add vendor prefixes when needed
   - Test across browsers
   - Provide fallbacks
   - Use feature detection

6. Debugging

```css
/* Slow down animations for debugging */
.debug-animations {
  animation-duration: 10s !important;
  transition-duration: 10s !important;
}
```
