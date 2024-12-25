
# Input Types

HTML5 introduced several new input types, expanding the capabilities of forms to improve user experience and data validation.

## Common Input Types:
1. **Text (`<input type="text">`)**
   - Default input type for single-line text.
   - Example:
   ```html
   <label for="name">Name:</label>
   <input type="text" id="name" name="name">
   ```

2. **Password (`<input type="password">`)**
   - Hides the entered characters for privacy.
   - Example:
   ```html
   <label for="password">Password:</label>
   <input type="password" id="password" name="password">
   ```

3. **Email (`<input type="email">`)**
   - Validates an email address format.
   - Example:
   ```html
   <label for="email">Email:</label>
   <input type="email" id="email" name="email">
   ```

4. **Number (`<input type="number">`)**
   - Accepts numeric input with optional constraints like `min` and `max`.
   - Example:
   ```html
   <label for="age">Age:</label>
   <input type="number" id="age" name="age" min="1" max="100">
   ```

5. **Date (`<input type="date">`)**
   - Provides a date picker interface.
   - Example:
   ```html
   <label for="dob">Date of Birth:</label>
   <input type="date" id="dob" name="dob">
   ```

6. **Checkbox (`<input type="checkbox">`)**
   - Used for toggling options.
   - Example:
   ```html
   <input type="checkbox" id="subscribe" name="subscribe" value="yes">
   <label for="subscribe">Subscribe to newsletter</label>
   ```

7. **Radio (`<input type="radio">`)**
   - Allows selection of one option from a group.
   - Example:
   ```html
   <input type="radio" id="male" name="gender" value="male">
   <label for="male">Male</label>
   ```

## Additional Input Types:
- **URL (`<input type="url">`)**: Validates web URLs.
- **Range (`<input type="range">`)**: Allows selection of a value within a range using a slider.
- **Color (`<input type="color">`)**: Provides a color picker interface.
- **Tel (`<input type="tel">`)**: Used for telephone numbers.
