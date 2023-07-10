# HTML Notes

## Table Of Contents

- [HTML Tables](#html-tables)
  * [Col and Colgroup](#col-and-colgroup)
  * [Captions](#captions)
  * [Adding Table Structure](#adding-table-structure)
- [Forms](#forms)

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

## Forms

To begin, we can enclose all the inputs a user will interact with on a form inside the `<form>` tags. The form element will then accept two essential attributes: `action` and `method`. 

- The `action` attribute will contain a URL value that tells the form where it should send its data to be processed.
- The `method` attribute tells the browser which HTTP request method it should use to submit the form. Two common form methods we will use are the `GET` and `POST` request methods. We use `GET` when we want to retrieve something from a server. We use `POST` to change something on the server,

### Form creation

We can create forms using form control elements. These allow us to interact with the form using buttons, text boxes, dropdowns and etc.

One of the most versatile form control elements is the `input` element.  It accepts a `type` attribute which tells the browser what type of data it should expect and how it should render the input element. Some different types of inputs we can use in our forms are as follows:

- Email inputs using `type="email"`.
- Password inputs using `type="password"`.
- Number inputs using `type="number"`.
- Date inputs using `type="date"`.
- Radio buttons using `type="radio"`. We make the browser know a group of elements is part of the same group of options by giving them all the inputs the same `name` attribute. We can also set the default selected radio button by adding the `checked` attribute to it.
- Checkboxes using `type="checkbox"`. Checkboxes are similar to radio buttons but they allow multiple options to be selected at once. Again, we can set checkboxes to be checked by default on page load by giving them a `checked` attribute.

Another element which is not technically an input though but still useful is the `<textarea>` element which allows users to enter a sizeable amount of free-form text, for example, a comment on a review or feedback form. The `<textarea>` element also has `rows` and `cols` attributes usually to allow us to specify an exact size for the `<textarea>` to take. 

We also give our inputs a label to inform users what type of data they are expected to enter. Labels accept a `for` attribute, which associates it with a particular input. The input we want to associate with a label needs an `id` attribute with the same value as the label’s `for` attribute.

We can also put placeholders on our input elements by attaching a `placeholder` attribute to an input. The value will be the placeholder text we want to display in the input.

Also, similar to how we use a `for` attribute for the labels, we use a `name` attribute for the input elements. We need to use labels so that users understand what the data entered into an input field will represent. Just like that, we also need to let the backend, where we send our data, know what each piece of data represents. This `name` attribute serves as a variable name for the input.

This is an example of a basic form with the content recapped above:

```HTML
<form action="example.com/path" method="post">
  <label for="first_name">First Name:</label>
  <input type="text" id="first_name" name="first_name" placeholder="Bob">
</form>
```

We should keep in mind that we can use any of the form control elements outside of the `<form>` element, even when we don’t have a backend server where we can send data.

#### Select Dropdowns

We can also make select dropdowns using the `<select>` element and then by displaying any options within the select element using `<option>` elements. All the option elements should have a value attribute which will be sent to the server when the form is submitted. We can also set one of the options to be the default selected element when the browser first renders the form by giving one of the options the selected attribute:

```HTML
<select name="Car">
  <option value="mercedes">Mercedes</option>
  <option value="tesla">Tesla</option>
  <option value="volvo" selected>Volvo</option>
  <option value="bmw">BMW</option>
  <option value="mini">Mini</option>
  <option value="ford">Ford</option>
</select>
```

We may also split the list of options into groups using the <optgroup> element. The optgroup element takes a label attribute which the browser uses as the label for each group:

```HTML
<select name="fashion">
  <optgroup label="Clothing">
    <option value="t_shirt">T-Shirts</option>
    <option value="sweater">Sweaters</option>
    <option value="coats">Coats</option>
  </optgroup>
  <optgroup label="Foot Wear">
    <option value="sneakers">Sneakers</option>
    <option value="boots">Boots</option>
    <option value="sandals">Sandals</option>
  </optgroup>
</select>
```

#### Buttons

We can create buttons using the `<button>` element. The content or text we want to have displayed inside the button will go within the opening and closing tags and the button element also accepts a `type` attribute that tells the browser which kind of button it is dealing with. There are three types of buttons available to us:

- Submit buttons using `type="submit"`
- Reset buttons using `type="reset"`
- Generic buttons using `type="button"`





