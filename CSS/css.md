# CSS Notes

## Table Of Contents

- [CSS Units](#css-units)
  * [Absolute Units](#absolute-units)
  * [Relative Units](#relative-units)
- [Text Styles](#text-styles)
- [CSS Properties](#css-properties)
- [Advanced Selectos](#advanced-selectors)
  * [Combinators](#combinators)
  * [Pseudo-classes and Pseudo-elements](#pseudo-classes-and-pseudo-elements)
  * [Attribute Selectors](#attribute-selectors)
- [Positioning](#positioning)
- [CSS Functions](#css-functions)
- [Custom Properties](#custom-properties)
- [CSS Grid](#css-grid)
  * [Explicit vs Implicit Grid](#explicit-vs-implicit-grid)
  * [Useful Grid Properties](#useful-grid-properties)

## CSS Units

There are many different units that we can use to define sizes in CSS. These can be classified as absolute, or relative units.

### Absolute Units

Absolute units are those that are always the same in any context - they are not relative to anything else and are generally considered to always be the same size. Some notable examples of absolute length units are as follows:

| Unit | Name                |
|------|---------------------|
| px   | Pixels              |
| cm   | Centimeters         |
| mm   | Millimeters         |
| Q    | Quarter-millimeters |
| in   | Inches              |
| pc   | Picas               |
| pt   | Points              |

Most of these units are more useful when used for print, rather than screen output. We typically only use px (pixels) for web development.

### Relative Units

Relative length units are relative to something else, perhaps the size of the parent element's font, or the viewport's size. The benefit of using relative units is that with some careful planning, we can make it so the size of text or other elements scales relative to everything else on the page. Some examples of the most useful relative units are as follows:

| Unit | Relative to...                                                                                                                                                            |
|------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| em   | The font size of the parent, in the case of typographical properties like `font size`, and the font size of the element itself, in the case of other properties like `width`. |
| rem  | The font size of the root element.                                                                                                                                        |
| ex   | The x-height of the element's font.                                                                                                                                       |
| ch   | The advance measure (width) of the glyph "0" of the element's font.                                                                                                       |
| lh   | The line height of the element.                                                                                                                                           |
| vw   | 1% of the viewport's width.                                                                                                                                               |
| vh   | 1% of the viewport's height.                                                                                                                                              |
| vmin | 1% of the viewport's smaller dimension.                                                                                                                                   |
| vmax | 1% of the viewport's larger dimension.                                                                                                                                    |

Between `em` and `rem`, `rem` should always be used as a rule of thumb for font sizing.

### Percentages, numbers and functions

We can also use percentages as they are always set relative to some other value. For example, if we set an element's `font-size` as a percentage, it will be a percentage of the `font-size` of the element's parent. If we use a percentage for a `width` value, it will be a percentage of the `width` of the parent.

We can also use numbers as some value types, an example being the `opacity` property, which controls the opacity of an element (how transparent it is). This property accepts a number between `0` (fully transparent) and `1` (fully opaque).

Furthermore, we can use functions within our CSS to give us the ability for doing simple calculations. For example, the `calc()` CSS function - is particularly useful if we want to work out values that we can't define when writing the CSS for projects, and need the browser to work out for us at runtime.

## Text Styles

### font-style

We typically use the `font-style` for italics. For example, we should use `font-style: italic;` if italics is required for styling purposes. As a rule of thumb, we should only aim to use the `em` element if italics is required for emphasis.

### letter-spacing

`letter-spacing` is another CSS text style we can use to, as the name suggests, change the space between letters in a word. For example, the following code:

```CSS
h1 {
  font-family: 'COUTUREBold';
  margin: 0;
  font-size: 38px;
}

.wide {
  font-size: 24px;
  letter-spacing: .5em;
}

.narrow {
  font-size: 48px;
  letter-spacing: -.15em;
}
```

Would reflect something like this:

![Screenshot 2023-07-02 at 4 51 19 PM](https://github.com/DevVivan/odin-project/assets/130225932/53d385bb-6b7e-4505-821d-a3e3258bf7f1)

### line-height

We can also use the `line-height` to adjust the spacing between lines in wrapped text. Adding a little line height can increase readability sometimes.

### text-transform

The `text-transform` property can be used to simply change the case of a given text, for example, from lowercase to uppercase. Syntax:

```CSS
/* Keyword values */
text-transform: none;
text-transform: capitalize;
text-transform: uppercase;
text-transform: lowercase;
text-transform: full-width;
text-transform: full-size-kana;

/* Global values */
text-transform: inherit;
text-transform: initial;
text-transform: revert;
text-transform: revert-layer;
text-transform: unset;
```

### text-shadow

The `text-shadow` property is best used sparingly, but it creates a great effect when used well. It essentially adds a shadow around the text in the selected element and is useful for headings or other presentational text. The syntax:

```CSS
/* offset-x | offset-y | blur-radius | color */
text-shadow: 1px 1px 2px black;

/* color | offset-x | offset-y | blur-radius */
text-shadow: #fc0 1px 0 10px;

/* offset-x | offset-y | color */
text-shadow: 5px 5px #558abb;

/* color | offset-x | offset-y */
text-shadow: white 2px 5px;

/* offset-x | offset-y
/* Use defaults for color and blur-radius */
text-shadow: 5px 10px;

/* Global values */
text-shadow: inherit;
text-shadow: initial;
text-shadow: revert;
text-shadow: revert-layer;
text-shadow: unset;
```

### ellipsis using `text-overflow`

With this `text-overflow` property, we can truncate overflowing text with an ellipsis. For example:

```CSS
.overflowing {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

## CSS Properties

### background

The `background` property is a shorthand for the following CSS properties:

- `background-attachment`
- `background-clip`
- `background-color`
- `background-image`
- `background-origin`
- `background-position`
- `background-repeat`
- `background-size`

### border & border-radius

The `border` property is a shorthand for 3 CSS properties:

- `border-color`
- `border-style`
- `border-width`

`border-radius` can be used to create rounded corners on elements. 

### overflow

The syntax for using the `overflow` property:

```CSS
/* Keyword values */
overflow: visible;
overflow: hidden;
overflow: clip;
overflow: scroll;
overflow: auto;
overflow: hidden visible;

/* Global values */
overflow: inherit;
overflow: initial;
overflow: revert;
overflow: revert-layer;
overflow: unset;
```

## Advanced Selectors

### Combinators

Alongside the descendant combinator, there are a few more CSS combinators as such:

- `>` - The child combinator
- `+` - The adjacent sibling combinator
- `~` - The general sibling combinator

### Pseudo-classes and Pseudo-elements

Pseudo-classes are selectors that select elements that are in a specific state, e.g. they are the first element of their type, or they are being hovered over by the mouse pointer. They are keywords that start with a single colon. For example, `:hover` is a pseudo-class.

#### Dynamic and User Action Pseudo-classes

These pseudo-classes can make pages feel much more dynamic and interactive.

- `:focus` applies to an element that is currently selected by the user either through selecting it with their cursor or using their keyboard.
- `:hover` will affect anything under the user’s mouse pointer. 
- `:active` applies to elements that are currently being clicked, and is especially useful for giving your user feedback that their action had an effect. 

#### Structural Pseudo-classes

These pseudo-classes can be used to select elements based on their position within the DOM.

- `:root` is a special class that represents the very top level of documents. It can be used to place ‘global’ CSS rules that are needed - such as custom properties and CSS variables. 
- `:first-child` and `:last-child` will match elements that are the first or last sibling.
- `:empty` will match elements that have no children at all, and `:only-child` will match elements that don’t have any siblings.

On the other hand, pseudo-elements allow us to affect parts of our HTML that aren’t elements at all. They are keywords that start with a double colon. For example:

- `::marker` allows us to customize the styling of `<li>` elements’ bullets or numbers.
- `::first-letter` and `::first-line` can be used to give special styling to the first letter or line of some text.
- `::selection` allows us to change the highlighting when a user selects text on the page.
- We can also use `::before` and `::after` to add extra elements to pages using CSS, instead of HTML.

### Attribute Selectors

We can use attribute selectors as a more flexible system to be able to target specific values. Some examples of attribute selectors are as follows:

- `[attribute]` - This general selector will select anything where the given attribute exists. 
- `selector[attribute]` - Attribute selectors can be combined with other types of selectors, such as class or element selectors.
- `[attribute="value"]` - `=` can be used to get more specific and to match a specific attribute with a specific value.
- `[attribute^="value"]` - `^=` Will match strings from the start.
- `[attribute$="value"]` - `$=` Will match strings from the end.
- `[attribute*="value"]` - `*=` The wildcard selector will match anywhere inside the string.

## Positioning

### static

`static` positioning is the default for every single page element. Different elements don’t have different default values for positioning, they all start out as static. Static doesn’t mean much; it just means that the element will flow into the page as it normally would. 

### relative

`relative` positioning means “relative to itself”. If we set `position: relative;` to an element but no other positioning attributes (top, left, bottom or right), it will have no effect on it’s positioning at all, it will be exactly as it would be if you left it as `position: static;` But if we do give it some other positioning attribute, say, `top: 10px;`, it will shift its position 10 pixels down from where it would normally be.

### absolute

`absolute` positioning allows us to place any page element exactly where we want it. We use the positioning attributes top, left, bottom, and right to set the location of the element. Absolute positioning removes elements from the normal document flow - meaning it can potentially cover some elements - and no space is created for the element in the page layout. The element is also positioned relative to the next parent element. If there is no such parent, it will default all the way back up to the `<html>` element itself meaning it will be placed relative to the page's viewport itself.

### fixed

`fixed` positioning positions elements relative to the viewport, or the browser window itself. The viewport doesn’t change when the window is scrolled, so a fixed-positioned element will stay right where it is when the page is scrolled.

### sticky

`sticky` positioning elements will just sit there like a static element, but as we scroll past it, if its parent element has room (usually: extra height) the sticky element will behave as if it’s fixed until that parent element is out of view. 

## CSS Functions

`calc()`

Performs basic arithmetic calculations on numerical values.

`min()`

Calculates the smallest of a list of values.

`max()`

Calculates the largest of a list of values.

`clamp()`

Calculates the central of minimum, central, and maximum values.

## Custom Properties

We can declare a custom property using a custom property name that begins with a double hyphen (--), and a property value that can be any valid CSS value. For example, using:

```CSS
element {
  --main-bg-color: brown;
}
```

We can then use the custom property value by specifying the custom property name inside the `var()` function, in place of a regular property value:

```CSS
element {
  background-color: var(--main-bg-color);
}
```

While there may be times when we want to limit the scope of a custom property, we may want to be able to use other custom properties on many, unrelated selectors. To do this, we can declare those custom properties on the `:root` pseudo-element, which is essentially the same thing as the `html` selector except it has a higher specificity. 

Custom properties can also be utilised to create themes, for example separate themes for dark mode and light mode, and we can also adapt according to the user's operation systemic using media queries.

## CSS Grid

For using Grid in CSS, we first make an element a grid container with the property `display: grid` or `display: inline-grid`. Then, only the direct child elements will become grid items. If we had another element as a child under one of these child elements it would not be a grid item. 

We can specify columns and rows using the properties `grid-template-columns` and `grid-template-rows`. For example, to create a grid of two columns and two rows to place 4 grid items:

```CSS
.container {
  display: grid;
  grid-template-columns: 50px 50px;
  grid-template-rows: 50px 50px;
}
```

We can do this using a single shorthand property too: the shorthand `grid-template` property. Here we can define our rows and columns all at once and rows are defined before the slash and columns are defined after the slash.

### Explicit vs Implicit Grid

When we add additional items to our container, they get slotted automatically into rows we did not define. This is because of the implicit grid concept and it’s how CSS Grid is able to automatically place grid items when we haven’t explicitly defined the layout for them. We can set the implicit grid track sizes using the `grid-auto-rows` and `grid-auto-columns` properties. In this way, we can ensure any new tracks the implicit grid makes for extra content are set at values that we defined. By default, CSS Grid will add additional content with implicit rows, but we can make additional content fit into columns using the `grid-auto-flow: column` property and those implicit track sizes can be defined with the `grid-auto-columns` property.

### Gap

We can adjust gap sizes for rows and columns separately using the `column-gap` and `row-gap` properties. Furthermore, we can use a shorthand property called `gap` to set both `row-gap` and `column-gap`.

### Positioning with Grid

We can also position cells using the `grid-column-start`, `grid-column-end`, `grid-row-start` and `grid-row-end` properties. There is also a shorthand to combine `grid-row-start` / `grid-column-start` / `grid-row-end` / `grid-column-end` into one line using `grid-area`.

We could do this to all of our grid items and give each item a `grid-area` value as a name. Then we can map out the whole structure with the grid container using `grid-template-areas`. We can also use a `.` to indicate empty cells.

### Useful Grid Properties

- Repeat: We can use the `repeat()` CSS function to define the number of rows or columns and the size we want them to be without having to manually type out each individual track’s size. For example:

  ```CSS
  .grid-container {
  grid-template-rows: repeat(2, 150px);
  grid-template-columns: repeat(5, 150px);
  }
  ```

- Fractional units: We can also use `fr` units as a way of distributing whatever remaining space is left in the grid. This allows grid items to fill up the entire width and height of the grid - essentially, stretch.
- We can use the `minmax()` and `clamp()` functions to make our grids more responsive too!
- Alongside the `repeat()` function, we can utilise `auto-fit` and `auto-fill` with `minmax()` to create some very cool responsive grid layouts. For example, using `repeat(auto-fit, minmax(150px, 1fr));` The difference between `auto-fit` and `auto-fill` is that when a grid is expanded to a size where another grid item could fit, but there aren’t any left, `auto-fit` will keep the grid items at their max size. However, when using `auto-fill`, the grid items will snap back down to their min size once the space becomes available to add another grid item, even if there isn’t one to be rendered. 
