# CSS Images and Media: Complete Guide

## Table of Contents

- [Image Basics](#image-basics)
- [Background Images](#background-images)
- [Image Properties](#image-properties)
- [Responsive Images](#responsive-images)
- [Media Properties](#media-properties)
- [Image Effects](#image-effects)
- [Best Practices](#best-practices)
- [Performance Optimization](#performance-optimization)

## Image Basics

### Basic Image Styling

```css
/* Basic image properties */
img {
  width: 300px;
  height: 200px;
  display: block;
  margin: auto;
}

/* Maintaining aspect ratio */
.responsive-img {
  max-width: 100%;
  height: auto;
}

/* Image fit options */
.cover-img {
  object-fit: cover;
  object-position: center;
}
```

### Object-Fit Properties

```css
.image {
  width: 300px;
  height: 200px;

  /* Different object-fit values */
  object-fit: fill; /* Stretch to fill */
  object-fit: contain; /* Keep aspect ratio, fit within */
  object-fit: cover; /* Cover entire area, crop if needed */
  object-fit: none; /* No resizing */
  object-fit: scale-down; /* Like contain, but never scales up */
}
```

## Background Images

### Basic Background Properties

```css
.background {
  /* Single background */
  background-image: url("image.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  /* Shorthand */
  background: url("image.jpg") center/cover no-repeat;
}

/* Multiple backgrounds */
.multiple-backgrounds {
  background: url("overlay.png") center/cover no-repeat, url("background.jpg")
      center/cover no-repeat;
}
```

### Background Size Options

```css
.background-sizing {
  /* Specific sizes */
  background-size: 300px 200px;

  /* Keywords */
  background-size: cover;
  background-size: contain;

  /* Percentage */
  background-size: 100% 100%;

  /* Auto */
  background-size: auto auto;
}
```

### Background Position

```css
.background-positioning {
  /* Keywords */
  background-position: top right;

  /* Percentages */
  background-position: 25% 75%;

  /* Specific values */
  background-position: 10px 20px;

  /* Edge offsets */
  background-position: right 20px bottom 10px;
}
```

## Image Properties

### Image Filters

```css
.image-filters {
  /* Basic filters */
  filter: brightness(1.2) contrast(1.1);

  /* Multiple filters */
  filter: grayscale(50%) sepia(20%) brightness(110%) contrast(110%) blur(1px);
}
```

### Clipping and Masking

```css
/* Clipping paths */
.clipped-image {
  clip-path: circle(50% at 50% 50%);
}

/* Complex shapes */
.polygon-clip {
  clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
}

/* Masking */
.masked-image {
  mask-image: linear-gradient(to bottom, black, transparent);
}
```

## Responsive Images

### Picture Element Styling

```css
/* Styling picture element */
picture {
  display: block;
  width: 100%;
}

picture img {
  width: 100%;
  height: auto;
}

/* Art direction use case */
@media (max-width: 768px) {
  picture img {
    object-position: left center;
  }
}
```

### Srcset Support

```css
/* Container for responsive images */
.img-container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
}

/* Responsive image styles */
.responsive-image {
  width: 100%;
  height: auto;
}
```

## Media Properties

### Video Styling

```css
video {
  width: 100%;
  max-width: 1200px;
  height: auto;

  /* Optional styles */
  object-fit: cover;
  background: #000;
}

/* Custom video controls */
.video-controls {
  background: rgba(0, 0, 0, 0.5);
  padding: 10px;
  border-radius: 4px;
}
```

### Audio Styling

```css
audio {
  width: 100%;
  max-width: 500px;
}

/* Custom audio player */
.audio-player {
  background: #f0f0f0;
  padding: 15px;
  border-radius: 8px;
}
```

## Image Effects

### Hover Effects

```css
.image-hover {
  transition: all 0.3s ease;
}

.image-hover:hover {
  transform: scale(1.1);
  filter: brightness(1.2);
}

/* Overlay effect */
.image-overlay {
  position: relative;
}

.image-overlay::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.image-overlay:hover::after {
  opacity: 1;
}
```

### Advanced Effects

```css
/* Parallax effect */
.parallax {
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 500px;
}

/* Ken Burns effect */
.ken-burns {
  animation: kenBurns 20s infinite;
}

@keyframes kenBurns {
  0% {
    transform: scale(1) translate(0);
  }
  50% {
    transform: scale(1.2) translate(-2%, -2%);
  }
  100% {
    transform: scale(1) translate(0);
  }
}
```

## Best Practices

1. **Loading Performance**

```css
/* Lazy loading styles */
.lazy-image {
  opacity: 0;
  transition: opacity 0.3s ease;
}

.lazy-image.loaded {
  opacity: 1;
}
```

2. **Accessibility**

```css
/* High contrast mode support */
@media (prefers-contrast: high) {
  img {
    border: 2px solid currentColor;
  }
}

/* Reduced motion */
@media (prefers-reduced-motion: reduce) {
  .ken-burns {
    animation: none;
  }
}
```

## Performance Optimization

### Image Loading Strategies

```css
/* Blur-up technique */
.blur-load {
  filter: blur(20px);
  transition: filter 0.3s ease;
}

.blur-load.loaded {
  filter: blur(0);
}

/* Progressive loading */
.progressive {
  transition: all 0.3s ease;
  position: relative;
}

.progressive::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #f0f0f0;
}
```

### Background Image Optimization

```css
/* Conditional loading */
@media (min-width: 768px) {
  .hero {
    background-image: url("large.jpg");
  }
}

@media (max-width: 767px) {
  .hero {
    background-image: url("small.jpg");
  }
}

/* WebP support */
@supports (background-image: -webkit-image-set(url("image.webp") 1x)) {
  .hero {
    background-image: -webkit-image-set(
      url("image.webp") 1x,
      url("image-2x.webp") 2x
    );
  }
}
```
