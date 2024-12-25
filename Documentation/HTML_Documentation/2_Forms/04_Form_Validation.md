
# Form Validation

HTML provides built-in form validation to ensure that users input data in the correct format before submission.

## Types of Validation:
1. **Required Fields**
   - Use the `required` attribute to make a field mandatory.
   - Example:
   ```html
   <label for="email">Email:</label>
   <input type="email" id="email" name="email" required>
   ```

2. **Pattern Matching**
   - Use the `pattern` attribute to specify a regular expression for validation.
   - Example:
   ```html
   <label for="zipcode">Zip Code:</label>
   <input type="text" id="zipcode" name="zipcode" pattern="\d{5}" title="Enter a 5-digit zip code">
   ```

3. **Input Length**
   - Use `minlength` and `maxlength` to set length constraints.
   - Example:
   ```html
   <label for="username">Username:</label>
   <input type="text" id="username" name="username" minlength="5" maxlength="15">
   ```

4. **Numeric Constraints**
   - Use `min`, `max`, and `step` attributes for numeric fields.
   - Example:
   ```html
   <label for="age">Age:</label>
   <input type="number" id="age" name="age" min="18" max="99">
   ```

5. **Email and URL Validation**
   - HTML automatically validates `type="email"` and `type="url"` inputs.
   - Example:
   ```html
   <label for="website">Website:</label>
   <input type="url" id="website" name="website">
   ```

## Validation Messages:
- Custom validation messages can be set using the `title` attribute.
- Example:
```html
<input type="text" id="code" name="code" pattern="[A-Za-z0-9]{6}" title="Must be a 6-character alphanumeric code">
```

## Benefits of HTML Validation:
- Reduces the need for client-side JavaScript validation.
- Provides a consistent user experience across browsers.
