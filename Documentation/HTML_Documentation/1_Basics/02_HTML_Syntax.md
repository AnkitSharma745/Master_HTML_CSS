# HTML Syntax

HTML syntax refers to the rules and structure used to create valid HTML documents. Understanding these rules is essential for building well-structured and error-free webpages.

## Basic HTML Syntax Rules

1. **HTML Tags:** Enclosed in angle brackets (`< >`) and usually come in pairs (opening and closing tags).
2. **Case Insensitivity:** HTML tags are not case-sensitive (`<P>` is the same as `<p>`), but lowercase is preferred.
3. **Attributes:** Provide additional information about an element, written in the opening tag.
4. **Nesting:** Tags must be properly nested.

### Example of Proper Nesting

```html
<p>This is a <strong>properly nested</strong> example.</p>
```

## HTML Document Structure

An HTML document generally follows this structure:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>Heading</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

### Explanation:

- `<!DOCTYPE html>`: Defines the document type.
- `<html>`: The root element.
- `<head>`: Contains metadata.
- `<body>`: Contains visible content.

## Example 1: HTML with Attributes

```html
<!DOCTYPE html>
<html>
  <head>
    <title>HTML Attributes Example</title>
  </head>
  <body>
    <h1 style="color: blue;">This is a blue heading</h1>
    <p title="Tooltip Example">Hover over this paragraph to see a tooltip.</p>
  </body>
</html>
```

### Explanation:

- `style`: Inline CSS style.
- `title`: Provides additional tooltip information.

## Example 2: Nested Elements

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Nesting Example</title>
  </head>
  <body>
    <p>This is a <strong>nested</strong> paragraph with <em>emphasis</em>.</p>
  </body>
</html>
```

### Explanation:

- `<strong>`: Bold text.
- `<em>`: Italic text.
