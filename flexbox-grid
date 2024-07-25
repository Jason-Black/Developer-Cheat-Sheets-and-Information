# CSS Flexbox and Grid Cheat Sheet

## Table of Contents

- [Introduction](#introduction)
- [Flexbox](#flexbox)
  - [Flex Container Properties](#flex-container-properties)
  - [Flex Item Properties](#flex-item-properties)
  - [Common Flexbox Layouts](#common-flexbox-layouts)
- [Grid](#grid)
  - [Grid Container Properties](#grid-container-properties)
  - [Grid Item Properties](#grid-item-properties)
  - [Common Grid Layouts](#common-grid-layouts)
- [Resources](#resources)
- [Summary Table](#summary-table)

## Introduction

CSS Flexbox and Grid are powerful layout systems that allow you to create complex, responsive layouts with ease. Flexbox is designed for one-dimensional layouts, while Grid is designed for two-dimensional layouts.

## Flexbox

### Flex Container Properties

The container element needs to have `display: flex` or `display: inline-flex` to become a flex container.

- **display: flex | inline-flex**
  - Turns an element into a flex container.

```css
.container {
  display: flex;
}
```

- **flex-direction**
  - Defines the direction of the main axis (row or column).
  - `row` (default), `row-reverse`, `column`, `column-reverse`.

```css
.container {
  flex-direction: row;
}
```

- **flex-wrap**
  - Defines whether flex items should wrap onto multiple lines.
  - `nowrap` (default), `wrap`, `wrap-reverse`.

```css
.container {
  flex-wrap: wrap;
}
```

- **flex-flow**
  - Shorthand for `flex-direction` and `flex-wrap`.
  - `flex-flow: <flex-direction> <flex-wrap>;`

```css
.container {
  flex-flow: row wrap;
}
```

- **justify-content**
  - Defines alignment along the main axis.
  - `flex-start` (default), `flex-end`, `center`, `space-between`, `space-around`, `space-evenly`.

```css
.container {
  justify-content: space-between;
}
```

- **align-items**
  - Defines alignment along the cross axis.
  - `stretch` (default), `flex-start`, `flex-end`, `center`, `baseline`.

```css
.container {
  align-items: center;
}
```

- **align-content**
  - Aligns flex lines when there is extra space on the cross axis.
  - `stretch` (default), `flex-start`, `flex-end`, `center`, `space-between`, `space-around`.

```css
.container {
  align-content: space-between;
}
```

### Flex Item Properties

Flex items are the children of a flex container.

- **order**
  - Controls the order of the flex items.
  - Default is 0, can be positive or negative.

```css
.item {
  order: 1;
}
```

- **flex-grow**
  - Defines how much a flex item should grow relative to the rest.
  - Default is 0 (do not grow).

```css
.item {
  flex-grow: 1;
}
```

- **flex-shrink**
  - Defines how much a flex item should shrink relative to the rest.
  - Default is 1 (shrink if needed).

```css
.item {
  flex-shrink: 1;
}
```

- **flex-basis**
  - Defines the default size of an element before the remaining space is distributed.
  - Can be a length (e.g., `20%`, `5rem`) or `auto`.

```css
.item {
  flex-basis: 20%;
}
```

- **flex**
  - Shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`.
  - `flex: <flex-grow> <flex-shrink> <flex-basis>;`

```css
.item {
  flex: 1 0 20%;
}
```

- **align-self**
  - Allows the default alignment (or the one specified by `align-items`) to be overridden for individual flex items.
  - `auto` (default), `flex-start`, `flex-end`, `center`, `baseline`, `stretch`.

```css
.item {
  align-self: flex-end;
}
```

### Common Flexbox Layouts

- **Centering a single item**

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh; /* Full viewport height */
}
```

- **Two-column layout**

```css
.container {
  display: flex;
  justify-content: space-between;
}

.left,
.right {
  flex: 1;
}
```

## Grid

### Grid Container Properties

The container element needs to have `display: grid` or `display: inline-grid` to become a grid container.

- **display: grid | inline-grid**
  - Turns an element into a grid container.

```css
.container {
  display: grid;
}
```

- **grid-template-columns**
  - Defines the columns of the grid with a space-separated list of values.
  - `none` (default), `repeat()`, `minmax()`, `auto`, `fr`.

```css
.container {
  grid-template-columns: 1fr 1fr 1fr; /* Three equal columns */
}
```

- **grid-template-rows**
  - Defines the rows of the grid with a space-separated list of values.
  - `none` (default), `repeat()`, `minmax()`, `auto`, `fr`.

```css
.container {
  grid-template-rows: 100px 200px; /* First row 100px, second row 200px */
}
```

- **grid-template-areas**
  - Defines a grid template by referencing the names of the grid areas which are specified with the `grid-area` property.

```css
.container {
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
}
```

- **grid-gap**
  - Shorthand for `grid-row-gap` and `grid-column-gap`.
  - `grid-gap: <row-gap> <column-gap>;`

```css
.container {
  grid-gap: 10px;
}
```

### Grid Item Properties

Grid items are the children of a grid container.

- **grid-column**
  - Shorthand for `grid-column-start` and `grid-column-end`.
  - Specifies a grid item's size and location within the grid column by contributing a line, a span, or nothing (automatic) to its grid placement.

```css
.item {
  grid-column: 1 / 3; /* Span from column line 1 to 3 */
}
```

- **grid-row**
  - Shorthand for `grid-row-start` and `grid-row-end`.
  - Specifies a grid item's size and location within the grid row by contributing a line, a span, or nothing (automatic) to its grid placement.

```css
.item {
  grid-row: 1 / 2; /* Span from row line 1 to 2 */
}
```

- **grid-area**
  - Specifies a grid item's size and location within the grid by contributing a line, a span, or nothing (automatic) to its grid placement.

```css
.item {
  grid-area: header;
}
```

### Common Grid Layouts

- **Simple Grid Layout**

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr;
  grid-gap: 10px;
}
```

- **Complex Grid Layout**

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  grid-template-columns: 1fr 3fr;
  grid-gap: 10px;
}

.header {
  grid-area: header;
}

.sidebar {
  grid-area: sidebar;
}

.main {
  grid-area: main;
}

.footer {
  grid-area: footer;
}
```

## Resources

- [CSS-Tricks Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS-Tricks Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [MDN Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
- [MDN Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)

## Summary Table

| Feature                | Syntax Example                                           | Description                                                     |
|------------------------|----------------------------------------------------------|-----------------------------------------------------------------|
| Flex Container         | `display: flex;`                                         | Defines a flex container                                        |
| Flex Direction         | `flex-direction: row;`                                   | Defines the direction of the flex items                         |
| Flex Wrap              | `flex-wrap: wrap;`                                       | Defines whether the flex items should wrap                      |
| Justify Content        | `justify-content: space-between;`                        | Defines alignment along the main axis                           |
| Align Items            | `align-items: center;`                                   | Defines alignment along the cross axis                          |
| Align Content          | `align-content: space-between;`                          | Aligns flex lines when there is extra space on the cross axis   |
| Flex Grow              | `flex-grow: 1;`                                          | Defines how much a flex item should grow                        |
| Flex Shrink            | `flex-shrink: 1;`                                        | Defines
