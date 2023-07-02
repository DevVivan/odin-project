# CSS Notes

## Table Of Contents

- [CSS Units](#css-units)
  * [Absolute Units](#absolute-units)
  * [Relative Units](#relative-units)
- [Text Styles](#text-styles)

## CSS Units

There are many different units that we can use to define sizes in CSS. These can be classified as absolute, or relative units.

### Absolute Units

Absolute units are those that are always the same in any context - they are not relative to anything else, and are generally considered to always be the same size. Some notable examples of absolute length units are as follows:

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

Relative length units are relative to something else, perhaps the size of the parent element's font, or the size of the viewport. The benefit of using relative units is that with some careful planning we can make it so the size of text or other elements scales relative to everything else on the page. Some examples of the most useful relative units are as follows:

| Unit | Relative to...                                                                                                                                                            |
|------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| em   | The font size of the parent, in the case of typographical properties like `font size`, and font size of the element itself, in the case of other properties like `width`. |
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

Furthermore, we can use functions within our CSS to give us the ability for doing simple calculations. For example, the `calc()` CSS function - which is particularly useful if we want to work out values that we can't define when writing the CSS for projects, and need the browser to work out for us at runtime.

## Text Styles

### font-style

We typically use the `font-style` for italics. For example, we should use `font-style: italic;` if italics is required for styling purposes. As a rule of thumb, we should only aim to use the `em` element if italics is required for emphasis.

### letter-spacing

`letter-spacing` is another CSS text style we can use to for, as the name suggests, change the space between letters in a word. For example, the following code:

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

We can also use the `line-height` to adjust spacing between lines in wrapped text. Adding a little line-height can increase readability sometimes.

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








