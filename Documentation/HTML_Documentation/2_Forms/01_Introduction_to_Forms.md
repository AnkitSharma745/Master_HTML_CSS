
# Introduction to Forms

Forms are a critical part of web development, allowing users to interact with web applications by submitting data. A form is a structured document that can collect user input and send it to a server for processing.

## Key Characteristics of Forms:
1. **Form Tag (`<form>`)**: Defines the beginning and end of a form.
2. **Attributes**:
   - `action`: Specifies the URL where form data should be submitted.
   - `method`: Specifies the HTTP method (`GET` or `POST`).
   - `enctype`: Specifies the encoding type for form data.

## Basic Syntax of a Form:
```html
<form action="/submit" method="post">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">
  <input type="submit" value="Submit">
</form>
```

## Form Workflow:
1. User fills out fields in the form.
2. User submits the form.
3. The form data is sent to the server specified in the `action` attribute.

## Importance of Forms:
- User authentication (login, signup).
- Collecting feedback and surveys.
- File uploads and multimedia submissions.
