# HTML Notes

## Table Of Contents

- [HTML Tables](#html-tables)
  * [Col and Colgroup](#col-and-colgroup)
  * [Captions](#captions)
  * [Adding Table Structure](#adding-table-structure)

## HTML Tables

To begin creating a table in HTML, use the `<table>` tags. Then, you can create table rows using `<tr>`. Further into the table, data can be displayed using the `<td>' tags. For example, this basic HTML table for a pair of dogs:

```HTML
    <table>
      <tr>
        <th>&nbsp;</th>
        <td>Dog 1</td>
        <td>Dog 2</td>
      </tr>
      <tr>
        <th>Breed</th>
        <td>Jack Russell</td>
        <td>Poodle</td>
      </tr>
      <tr>
        <th>Age</th>
        <td>16</td>
        <td>9</td>
      </tr>
      <tr>
        <th>Owner</th>
        <td>Mother-in-law</td>
        <td>Me</td>
      </tr>
      <tr>
        <th>Eating Habits</th>
        <td>Eats everyone's leftovers</td>
        <td>Nibbles at food</td>
      </tr>
    </table>
```

Would appear somewhat like this:

<img width="498" alt="Screenshot 2023-06-28 at 8 36 12 PM" src="https://github.com/DevVivan/odin-project/assets/130225932/bef37bb0-df4d-43c3-8e91-d7513c07d853">

We can also use the `rowspan` and `colspan` attributes in our different table tags to make cells span multiple rows or columns.

### Col and Colgroup

The `<colgroup>` tag specifies a group of one or more columns in a table for formatting. It is useful for applying styles to entire columns, instead of repeating the styles for each cell, for each row.

To define different properties to a column within a `<colgroup>`, use the `<col>` tag within the `<colgroup>` tag.

### Captions

We can also give tables a caption by putting them inside a `<caption>` element and nesting that inside the `<table>` element. These captions should be put directly below the opening `<table>` tag. For example:

```HTML
<table>
  <caption>
    Dinosaurs in the Jurassic period
  </caption>

  …
</table>
```

### Adding Table Structure

As tables gradually become more and more complex, it is best to add table structure using `<thead>`, `<tfoot>`, and `<tbody>`, which all allow you to mark up a header, footer, and body section for tables.

- The <thead> element must wrap the part of the table that is the header — this is usually the first row containing the column headings, but this is not necessarily always the case.
- The <tfoot> element needs to wrap the part of the table that is the footer — this might be a final row with items in the previous rows summed, for example. 
- The <tbody> element needs to wrap the other parts of the table content that aren't in the table header or footer. 