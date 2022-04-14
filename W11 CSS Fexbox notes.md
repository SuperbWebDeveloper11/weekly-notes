# `CSS Flexible Box Model`

## `The following notes are covered in this file`

- Introduction
- The two axes of flexbox
- Flex Container (flex-direction, flex-wrap, flex-flow, justify-content, align-items and align-content)
- Flex Items (order, flex-grow, flex-shrink, flex-basis, flex and align-self)
- Perfect Centering

## `Introduction`

The Flexible Box Module, usually referred to as flexbox, was designed as a **one-dimensional layout model**, and as a method that could offer space distribution between items in an interface and powerful alignment capabilities.

When we describe flexbox as being one dimensional we are describing the fact that flexbox deals with layout in one dimension at a time — either as a row or as a column. This can be contrasted with the two-dimensional model of CSS Grid Layout, which controls columns and rows together.

To start using the Flexbox model, you need to first define a flex container and flex items inside of it.

## `The two axes of flexbox`

When working with flexbox you need to think in terms of two axes — the main axis and the cross axis.
The **main axis** is defined by the flex-direction property, and the **cross axis** runs perpendicular to it.

## `Flex Container`

The flex container becomes flexible by setting the display property to flex

```css
.flex-container {
  display: flex;
}
```

Other flex container properties are: flex-direction, flex-wrap, flex-flow, justify-content, align-items and align-content

### `flex-direction`

The flex-direction property defines in which direction the container wants to stack the flex items.

```html
<div class="flex-container">
  <div class="flex-item">Item 1</div>
  <div class="flex-item">Item 2</div>
  <div class="flex-item">Item 3</div>
</div>
```

```css
.flex-container {
  background-color: rgb(226, 192, 129);
  height: 100vh;
  display: flex;
  flex-direction: row; /* this is the default */
  /* flex-direction: row-reverse; */
  /* flex-direction: column; */
  /* flex-direction: column-reverse; */
}

.flex-container .flex-item {
  width: 100px;
  height: 100px;
  margin: 10px;
  padding: 10px;
  background-color: rgb(133, 91, 13);
  color: rgb(255, 255, 255);
  border-radius: 5px;
}
```

### `flex-wrap`

The flex-wrap property specifies whether the flex items should wrap or not.

```html
<div class="flex-container">
  <div class="flex-item">Item 1</div>
  <div class="flex-item">Item 2</div>
  <div class="flex-item">Item 3</div>
  <div class="flex-item">Item 4</div>
  <div class="flex-item">Item 5</div>
  <div class="flex-item">Item 6</div>
  <div class="flex-item">Item 7</div>
  <div class="flex-item">Item 8</div>
  <div class="flex-item">Item 9</div>
</div>
```

```css
.flex-container {
  background-color: rgb(226, 192, 129);
  height: 100vh;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  flex-wrap: nowrap; /* Default */
  flex-wrap: wrap-reverse;
}
```

### `flex-flow`

The flex-flow property is a shorthand property for setting both the flex-direction and flex-wrap properties.

```css
.flex-container {
  display: flex;
  flex-flow: row wrap;
}
```

### `justify-content`

The justify-content property is used to align the flex items on the **main axis**

```css
.flex-container {
  display: flex;
  justify-content: flex-start; /* default */
  justify-content: flex-end;
  justify-content: center;
  justify-content: space-around;
  justify-content: space-between;
}
```

### `align-items`

The align-items property is used to align the flex items on the **cross axis**

```css
.flex-container {
  display: flex;
  align-items: flex-start; /* default */
  align-items: flex-end;
  align-items: center;
  align-items: stretch;
  align-items: baseline;
}
```

### `align-content`

The align-content property is used to **align the flex lines** on the **cross axis**

```css
.flex-container {
  display: flex;
  align-content: flex-start; /* default */
  align-content: flex-end;
  align-content: center;
  align-content: stretch;
  align-content: baseline;
  align-content: space-around;
  align-content: space-between;
}
```

## `Flex Items`

The direct child elements of a flex container automatically becomes flexible (flex) items.

The flex item properties are: (order, flex-grow, flex-shrink, flex-basis, flex and align-self)

### `order`

```html
<div class="flex-container">
  <div class="flex-item" style="order: 2">Item 1</div>
  <div class="flex-item" style="order: 1">Item 2</div>
  <div class="flex-item" style="order: 3">Item 3</div>
</div>
```

### `flex-basis`

The flex-basis property specifies the initial length of a flex item.

```html
<div class="flex-container">
  <div class="flex-item" style="flex-basis: 200px">Item 1</div>
  <div class="flex-item" style="flex-basis: 200px">Item 2</div>
  <div class="flex-item" style="flex-basis: 200px">Item 3</div>
</div>
```

### `flex-grow`

The flex-grow property specifies how much a flex item will grow relative to the rest of the flex items (when the screen size is smaller than the total width of all items).

```html
<div class="flex-container">
  <div class="flex-item" style="flex-grow: 1">Item 1</div>
  <div class="flex-item" style="flex-grow: 4">Item 2</div>
  <div class="flex-item" style="flex-grow: 1">Item 3</div>
</div>
```

### `flex-shrink`

The flex-shrink property specifies how much a flex item will shrink relative to the rest of the flex items (when the screen size is smaller than the total width of all items).

```html
<div class="flex-container">
  <div class="flex-item" style="flex-shrink: 1">Item 1</div>
  <div class="flex-item" style="flex-shrink: 4">Item 2</div>
  <div class="flex-item" style="flex-shrink: 1">Item 3</div>
</div>
```

### `flex`

The flex property is a shorthand property for the flex-grow, flex-shrink, and flex-basis properties.

```html
<div class="flex-container">
  <div class="flex-item" style="flex: 1 0 0">Item 1</div>
  <div class="flex-item" style="flex: 1">Item 2</div>
  <div class="flex-item" style="flex: 1">Item 3</div>
</div>
```

### `align-self`

The align-self property specifies the alignment for the selected item inside the flexible container.

The align-self property overrides the default alignment set by the container's align-items property.

```html
<div class="flex-container">
  <div class="flex-item" style="align-self: flex-start">Item 1</div>
  <div class="flex-item" style="align-self: center">Item 2</div>
  <div class="flex-item">Item 3</div>
</div>
```

## `Perfect Centering`

In the following example we will solve a very common style problem which is perfect centering.

```css
.flex-container {
  display: flex;
  height: 300px;
  justify-content: center;
  align-items: center;
}
```
