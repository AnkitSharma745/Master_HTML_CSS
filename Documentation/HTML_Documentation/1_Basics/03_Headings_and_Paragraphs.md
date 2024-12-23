# Headings and Paragraphs in HTML

Headings and paragraphs are essential for organizing and displaying text content on a webpage.

## Headings

HTML provides six levels of headings, from `<h1>` (highest importance) to `<h6>` (lowest importance).

### Syntax:

```html
<h1>This is a Heading 1</h1>
<h2>This is a Heading 2</h2>
<h3>This is a Heading 3</h3>
<h4>This is a Heading 4</h4>
<h5>This is a Heading 5</h5>
<h6>This is a Heading 6</h6>
```

### Explanation:

- `<h1>`: Main heading, usually used for the page title.
- `<h2>` to `<h6>`: Subheadings in descending importance.

## Paragraphs

Paragraphs are used to group blocks of text together.

### Syntax:

```html
<p>This is a paragraph of text.</p>
```

### Explanation:

- `<p>`: Defines a paragraph.
- Text is displayed with line breaks before and after.

## Example 1: Headings and Paragraphs Together

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Headings and Paragraphs</title>
  </head>
  <body>
    <h1>Main Heading</h1>
    <p>This is a paragraph under the main heading.</p>
    <h2>Subheading</h2>
    <p>This is another paragraph under a subheading.</p>
  </body>
</html>
```

### Explanation:

- The heading tags organize content hierarchically.
- Paragraph tags group related text content.

## Example 2: Styling Headings and Paragraphs

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Styled Headings and Paragraphs</title>
    <style>
      h1 {
        color: green;
      }
      p {
        font-size: 14px;
        line-height: 1.5;
      }
    </style>
  </head>
  <body>
    <h1>Styled Heading</h1>
    <p>This paragraph has custom styling applied using CSS.</p>
  </body>
</html>
```

### Explanation:

- `h1 { color: green; }`: Sets heading color to green.
- `p { font-size: 14px; line-height: 1.5; }`: Customizes text size and spacing.
