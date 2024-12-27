# CSS Float and Clear

## Float Property

```css
float: none | left | right | inherit;
```

### Core Concepts

- Removes element from normal document flow
- Element shifts left/right until touching container or another float
- Text/inline elements wrap around floated elements
- Container may collapse if contains only floated elements

### Common Use Cases

1. Text Wrap Around Images

```css
img {
  float: left;
  margin: 0 1em 1em 0;
}
```

2. Multi-column Layouts

```css
.column {
  float: left;
  width: 33.33%;
  padding: 15px;
  box-sizing: border-box;
}
```

## Clear Property

```css
clear: none | left | right | both | inherit;
```

### Clearing Techniques

1. Clear Property

```css
.element {
  clear: both;
}
```

2. Clearfix Hack

```css
.clearfix::after {
  content: "";
  display: block;
  clear: both;
  visibility: hidden;
  height: 0;
}
```

3. Modern Alternative (overflow)

```css
.container {
  overflow: auto;
}
```

## Best Practices

1. Layout Considerations

- Use Flexbox/Grid for modern layouts
- Reserve float for text-wrap scenarios
- Consider document flow impact

2. Performance

- Minimize floated elements
- Use proper clearing methods
- Avoid deep float nesting

3. Common Issues

- Container collapse
- Unwanted text wrap
- Overlapping elements
- Margin collapsing

## Browser Support

- Universal support
- No vendor prefixes needed
- Works in legacy browsers

## Debugging Tips

```css
/* Debug outline */
* {
  outline: 1px solid red;
}

/* Force clear */
.debug-clear {
  clear: both !important;
}
```

## Modern Alternatives

1. Flexbox Layout
2. CSS Grid
3. Multi-column Layout
4. Writing Mode

## Legacy Support Notes

- Essential for maintaining older websites
- Important for email templates
- Fallback for modern layout methods
