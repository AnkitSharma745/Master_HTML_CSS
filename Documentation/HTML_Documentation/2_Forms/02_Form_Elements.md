
# Form Elements

HTML forms contain various elements that collect user input. These elements are defined using specific tags and attributes.

## Common Form Elements:
1. **Text Input (`<input type="text">`)**
   - Used to collect single-line text input.
   - Example:
   ```html
   <label for="username">Username:</label>
   <input type="text" id="username" name="username">
   ```

2. **Password Input (`<input type="password">`)**
   - Masks the input to hide sensitive data.
   - Example:
   ```html
   <label for="password">Password:</label>
   <input type="password" id="password" name="password">
   ```

3. **Radio Buttons (`<input type="radio">`)**
   - Allows the user to select one option from a group.
   - Example:
   ```html
   <p>Gender:</p>
   <input type="radio" id="male" name="gender" value="male">
   <label for="male">Male</label>
   <input type="radio" id="female" name="gender" value="female">
   <label for="female">Female</label>
   ```

4. **Checkboxes (`<input type="checkbox">`)**
   - Allows multiple selections from a list of options.
   - Example:
   ```html
   <p>Hobbies:</p>
   <input type="checkbox" id="hobby1" name="hobby" value="reading">
   <label for="hobby1">Reading</label>
   <input type="checkbox" id="hobby2" name="hobby" value="traveling">
   <label for="hobby2">Traveling</label>
   ```

5. **Dropdown (`<select>`)**
   - Provides a list of options in a dropdown menu.
   - Example:
   ```html
   <label for="country">Country:</label>
   <select id="country" name="country">
     <option value="india">India</option>
     <option value="usa">USA</option>
     <option value="uk">UK</option>
   </select>
   ```

6. **Submit Button (`<input type="submit">` or `<button>`)**
   - Submits the form data to the server.
   - Example:
   ```html
   <input type="submit" value="Submit">
   ```

## Advanced Elements:
- **File Upload (`<input type="file">`)**:
  Allows users to upload files.
- **Hidden Inputs (`<input type="hidden">`)**:
  Stores data without displaying it to the user.
