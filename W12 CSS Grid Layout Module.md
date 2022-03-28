# CSS Grid Layout Module

## Topics

- Introduction
- Grid Gaps
- Grid Lines
- Grid Container
- grid-template-columns Property
- grid-template-rows Property
- align-content Property
- justify-content Property
- Grid Items
- Grid Lines

## Introduction

The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.
An HTML element becomes a grid container when its display property is set to grid or inline-grid.

```css
.grid-container {
  display: grid;
}
```

The vertical lines of grid items are called columns.
The horizontal lines of grid items are called rows.

## Grid Gaps

The spaces between each column/row are called gaps.

```css
.grid-container {
  display: grid;
  column-gap: 20px;
  row-gap: 20px;
  gap: 20px; /* This is a shorthand property for the row-gap and the column-gap properties */
}
```

## Grid Container

Grid containers consist of grid items, placed inside columns and rows.

## grid-template-columns Property

The grid-template-columns property defines the number of columns in your grid layout, and it can define the width of each column.
If you have more than 4 items in a 4 columns grid, the grid will automatically add a new row to put the items in.

```css
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto;
  grid-template-columns: repeat(4, auto); /* shorthand */
}
```

## grid-template-rows Property

The grid-template-rows property defines the height of each row.
If you have more than 4 items in a 4 columns grid, the grid will automatically add a new row to put the items in.

```css
.grid-container {
  display: grid;
  grid-template-rows: 80px 200px;
  grid-auto-rows: minmax(
    100px,
    auto
  ); /* you can also define the height using minmax function */
}
```

## justify-content Property

The justify-content property is used to align the whole grid inside the container.
The grid's total width has to be less than the container's width for the justify-content property to have any effect.

```css
.grid-container {
  display: grid;
  justify-content: space-evenly;
}
```

## align-content Property

The align-content property is used to vertically align the whole grid inside the container.
The grid's total height has to be less than the container's height for the align-content property to have any effect.

```css
.grid-container {
  display: grid;
  height: 400px;
  align-content: center;
}
```

## Grid Items

A grid container contains grid items.

By default, a container has one grid item for each column, in each row, but you can style the grid items so that they will span multiple columns and/or rows.

## Grid Lines

The lines between columns are called **column lines**.
The lines between rows are called **row lines**.

```css
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 10px;
}

.item1 {
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 3;
}
```

```html
<div class="grid-container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
  <div class="item6">6</div>
  <div class="item7">7</div>
  <div class="item8">8</div>
</div>
```

## Naming Grid Items

Name all items, and make a ready-to-use webpage template:

```css
.item1 {
  grid-area: header;
}
.item2 {
  grid-area: menu;
}
.item3 {
  grid-area: main;
}
.item4 {
  grid-area: right;
}
.item5 {
  grid-area: footer;
}

.grid-container {
  grid-template-areas:
    "header header header header header header"
    "menu main main main right right"
    "menu footer footer footer footer footer";
}
```
