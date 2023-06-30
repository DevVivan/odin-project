# CSS Notes

## Table Of Contents

- [CSS Units](#css-units)
  * [Absolute Units](#absolute-units)
  * [Relative Units](#relative-units)

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

Between `em` and `rem`, `rem` should always be used as a rule of thumb.

