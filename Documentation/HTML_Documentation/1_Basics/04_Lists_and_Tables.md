# Lists and Tables in HTML

Lists and tables are used to organize and present data in a structured manner on web pages.

## Lists

HTML supports two main types of lists:

1. **Ordered Lists (`<ol>`)**: Display items in a numbered format.
2. **Unordered Lists (`<ul>`)**: Display items with bullet points.

### Example of an Ordered List:

```html
<ol>
  <li>First Item</li>
  <li>Second Item</li>
  <li>Third Item</li>
</ol>
```

# HTML Tags Related to Tables This document provides comprehensive information

about HTML tags and attributes used to create and style tables in web
development.

````html
<table>
  `: Table Tag - **Description**: The `
  <table>
    ` tag defines a table structure in HTML. - **Attributes**: - `border`:
    Specifies the width of the border around the table. (Deprecated; use CSS
    instead) - `cellpadding`: Specifies the space between the cell content and
    the cell border. (Deprecated; use CSS instead) - `cellspacing`: Specifies
    the space between cells. (Deprecated; use CSS instead) - `summary`: Provides
    a summary of the table's content for screen readers. (Obsolete) ## `
    <caption>
      `: Table Caption Tag - **Description**: Provides a title or caption for
      the table, typically displayed above it. - **Attributes**: None specific.
      ## `
      <thead>
        `: Table Head Tag - **Description**: Groups header content in the table,
        typically containing column headings. ## `
      </thead>

      <tbody>
        `: Table Body Tag - **Description**: Groups the main content of the
        table, excluding headers and footers. ## `
      </tbody>

      <tfoot>
        `: Table Footer Tag - **Description**: Groups footer content in the
        table, often used for summary rows. ## `
        <tr>
          `: Table Row Tag - **Description**: Defines a row in a table. ## `
          <th>
            `: Table Header Cell Tag - **Description**: Defines a header cell in
            a table, usually displayed in bold and centered. - **Attributes**: -
            `colspan`: Specifies the number of columns the cell should span. -
            `rowspan`: Specifies the number of rows the cell should span. -
            `scope`: Specifies the set of data the header relates to (`col`,
            `row`, `colgroup`, `rowgroup`). ## `
          </th>

          <td>
            `: Table Data Cell Tag - **Description**: Defines a standard data
            cell in a table. - **Attributes**: - `colspan`: Specifies the number
            of columns the cell should span. - `rowspan`: Specifies the number
            of rows the cell should span. - `headers`: Lists the IDs of `
          </td>

          <th>
            ` elements the cell is associated with. ## `
            <colgroup>
              `: Column Group Tag - **Description**: Specifies a group of
              columns in a table for styling purposes. - **Attributes**: -
              `span`: Specifies the number of columns the group should span. ##
              `
              <col />
              `: Column Tag - **Description**: Defines individual columns within
              a `
              <colgroup>
                `. - **Attributes**: - `span`: Specifies the number of columns
                the tag should span. ## Accessibility and Best Practices - **Use
                Headers**: Use `
                <th>
                  ` and the `scope` attribute to ensure clear association
                  between headers and data. - **ARIA Roles**: Apply ARIA roles
                  like `role="table"`, `role="row"`, and `role="cell"` for
                  enhanced accessibility. - **Responsive Design**: Use CSS or
                  frameworks to make tables responsive. ## Example Code ###
                  Basic Table ```html
                  <table border="1">
                    <caption>
                      Sample Table
                    </caption>
                    <thead>
                      <tr>
                        <th>Name</th>
                        <th>Age</th>
                        <th>City</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <td>Alice</td>
                        <td>25</td>
                        <td>New York</td>
                      </tr>
                      <tr>
                        <td>Bob</td>
                        <td>30</td>
                        <td>Los Angeles</td>
                      </tr>
                    </tbody>
                    <tfoot>
                      <tr>
                        <td colspan="3">End of Data</td>
                      </tr>
                    </tfoot>
                  </table>
                </th>
              </colgroup>
            </colgroup>
          </th>
        </tr>
      </tfoot>
    </caption>
  </table>
</table>

<table>
  <colgroup>
    <col style="background-color: #f2f2f2" />
    <col style="background-color: #e6e6e6" />
    <col style="background-color: #cccccc" />
  </colgroup>
  <thead>
    <tr>
      <th>Product</th>
      <th>Price</th>
      <th>Quantity</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Apples</td>
      <td>$2.00</td>
      <td>50</td>
    </tr>
    <tr>
      <td>Oranges</td>
      <td>$1.50</td>
      <td>75</td>
    </tr>
  </tbody>
</table>
````
