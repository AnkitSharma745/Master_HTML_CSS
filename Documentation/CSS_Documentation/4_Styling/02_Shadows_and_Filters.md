# CSS Shadows and Filters: Complete Guide

## Table of Contents

- [Definitions](#definitions)
- [Box Shadows](#box-shadows)
- [Text Shadows](#text-shadows)
- [CSS Filters](#css-filters)
- [Backdrop Filters](#backdrop-filters)
- [Drop Shadows](#drop-shadows)
- [Performance Tips](#performance-tips)
- [Browser Support](#browser-support)

## Definitions

### Shadow Terms

- **Box Shadow**: A visual effect that adds a shadow effect around an element's frame
- **Text Shadow**: A visual effect that adds a shadow behind text content
- **Offset**: The distance the shadow is pushed away from the element
- **Blur Radius**: How blurry or sharp the shadow appears
- **Spread Radius**: How much the shadow expands
- **Inset Shadow**: A shadow that appears inside the element rather than outside

### Filter Terms

- **Filter**: A visual effect applied to an element that modifies its appearance
- **Backdrop Filter**: A filter effect applied to the area behind an element
- **Primitive Filter**: Basic filter operations that can be combined
- **Filter Function**: CSS functions that apply predefined filter effects
- **SVG Filter**: Complex custom filters defined using SVG

## Box Shadows

### Basic Syntax

```css
/* Syntax */
box-shadow: offset-x offset-y blur-radius spread-radius color;

/* Examples */
.basic-shadow {
  box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
}

/* Multiple Shadows */
.multiple-shadows {
  box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2), -2px -2px 4px rgba(255, 255, 255, 0.5);
}

/* Inset Shadow */
.inset-shadow {
  box-shadow: inset 2px 2px 4px rgba(0, 0, 0, 0.2);
}
```

### Advanced Shadow Techniques

```css
/* Layered Shadows */
.layered {
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.12), 0 2px 2px rgba(0, 0, 0, 0.12),
    0 4px 4px rgba(0, 0, 0, 0.12), 0 8px 8px rgba(0, 0, 0, 0.12);
}

/* Neon Glow */
.neon {
  box-shadow: 0 0 5px #fff, 0 0 10px #fff, 0 0 20px #0ff, 0 0 30px #0ff;
}
```

## Text Shadows

### Basic Text Shadow

```css
/* Syntax */
text-shadow: offset-x offset-y blur-radius color;

/* Examples */
.basic-text-shadow {
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

/* Multiple Text Shadows */
.multiple-text-shadows {
  text-shadow: 2px 2px 0 #ff0000, -2px -2px 0 #00ff00;
}
```

### Creative Text Effects

```css
/* 3D Text Effect */
.text-3d {
  text-shadow: 1px 1px 1px #919191, 1px 2px 1px #919191, 1px 3px 1px #919191, 1px
      4px 1px #919191;
}

/* Neon Text */
.text-neon {
  text-shadow: 0 0 5px #fff, 0 0 10px #fff, 0 0 20px #ff00de, 0 0 30px #ff00de,
    0 0 40px #ff00de;
}
```

## CSS Filters

### Basic Filter Functions

```css
/* Syntax */
filter: function(value);

/* Examples */
.element {
  /* Blur */
  filter: blur(5px);

  /* Brightness */
  filter: brightness(150%);

  /* Contrast */
  filter: contrast(200%);

  /* Grayscale */
  filter: grayscale(100%);

  /* Hue Rotate */
  filter: hue-rotate(90deg);

  /* Invert */
  filter: invert(100%);

  /* Opacity */
  filter: opacity(50%);

  /* Saturate */
  filter: saturate(200%);

  /* Sepia */
  filter: sepia(100%);
}
```

### Multiple Filters

```css
.multi-filter {
  filter: contrast(150%) brightness(110%) sepia(30%) blur(1px);
}
```

## Backdrop Filters

### Basic Backdrop Filters

```css
/* Syntax */
backdrop-filter: function(value);

/* Examples */
.glass-effect {
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
}

.dark-backdrop {
  backdrop-filter: brightness(50%) blur(4px);
}
```

## Drop Shadows

### Filter Drop Shadow vs Box Shadow

```css
/* Filter Drop Shadow */
.filter-shadow {
  filter: drop-shadow(3px 3px 2px rgba(0, 0, 0, 0.3));
}

/* Comparison with Box Shadow */
.box-shadow {
  box-shadow: 3px 3px 2px rgba(0, 0, 0, 0.3);
}
```

## Performance Tips

1. **Shadow Performance**

   - Use `box-shadow` sparingly on elements that animate
   - Consider using transforms instead of box-shadow for animations
   - Avoid multiple complex shadows on frequently animated elements

2. **Filter Performance**

   - Use hardware acceleration when possible (`transform: translateZ(0)`)
   - Minimize the number of filtered elements on page
   - Consider using CSS properties instead of filters when possible

3. **Backdrop Filter Performance**
   - Use backdrop-filter only when necessary
   - Consider fallbacks for unsupported browsers
   - Test performance on mobile devices

## Browser Support

### Modern Browsers

- Box Shadow: Fully supported
- Text Shadow: Fully supported
- CSS Filters: Well supported in modern browsers
- Backdrop Filters: Growing support, check for specific browser compatibility

### Vendor Prefixes

```css
.element {
  -webkit-filter: blur(5px);
  filter: blur(5px);

  -webkit-backdrop-filter: blur(10px);
  backdrop-filter: blur(10px);
}
```

## Examples of Combined Effects

### Glass Morphism

```css
.glass {
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
```

### Floating Card

```css
.floating-card {
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1), 0 6px 6px rgba(0, 0, 0, 0.1);
  filter: brightness(100%) contrast(100%);
  transition: all 0.3s ease;
}

.floating-card:hover {
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.15), 0 10px 10px rgba(0, 0, 0, 0.12);
  filter: brightness(105%) contrast(105%);
}
```
