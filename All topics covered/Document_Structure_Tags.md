
# HTML Document Structure Tags

## Overview
HTML document structure tags define the basic framework and layout of an HTML document. These tags ensure the proper organization of content and provide essential metadata for the browser and search engines.

## Tags

### 1. `<!DOCTYPE>`
- Defines the document type and version of HTML.
- Example:
  ```html
  <!DOCTYPE html>
  ```

### 2. `<html>`
- The root element of an HTML document.
- Attributes:
  - `lang`: Specifies the language of the document.
- Example:
  ```html
  <html lang="en">
  </html>
  ```

### 3. `<head>`
- Contains metadata and links to external resources like stylesheets and scripts.
- Example:
  ```html
  <head>
      <title>Document Title</title>
  </head>
  ```

### 4. `<body>`
- Contains the visible content of the document.
- Example:
  ```html
  <body>
      <h1>Welcome!</h1>
  </body>
  ```

### 5. `<title>`
- Sets the title of the web page (displayed in the browser tab).
- Example:
  ```html
  <title>My Website</title>
  ```

### 6. `<meta>`
- Provides metadata about the document.
- Common attributes:
  - `charset`: Specifies character encoding.
  - `name` and `content`: Provide additional metadata like description or keywords.
- Example:
  ```html
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  ```

### 7. `<link>`
- Links external resources to the document.
- Common use: Link stylesheets.
- Example:
  ```html
  <link rel="stylesheet" href="styles.css">
  ```

### 8. `<script>`
- Embeds or links to JavaScript code.
- Example:
  ```html
  <script src="script.js"></script>
  ```

### 9. `<style>`
- Embeds CSS styles directly into the document.
- Example:
  ```html
  <style>
      body {
          background-color: lightblue;
      }
  </style>
  ```

## Summary
These tags form the foundational structure of an HTML document and are essential for every web page.
