# CSS Media Query Notes

## These Notes are Cover the Following Topics

- What is a Media Query?
- Add a Breakpoint
- Always Design for Mobile First
- Typical Device Breakpoints
- Orientation: Portrait / Landscape
- Hide Elements With Media Queries

## What is a Media Query?

Media Queries CSS technique introduced in CSS3 that allows us to create Responsive website

## Add a Breakpoint

Using Media Queries we can add breakpoints and apply the design according to these breakpoints

```css
/* This style works only on screens (other media types are: all, print and speech) and when the width is above or equal 600px */
@media only screen and (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

## Always Design for Mobile First

Mobile First means designing for mobile before designing for desktop or any other device (This will make the page display faster on smaller devices).

## Typical Device Breakpoints

There are tons of screens and devices with different heights and widths, so it is hard to create an exact breakpoint for each device. To keep things simple you could target five groups:

```css
/* Extra small devices (phones, 600px and down) */
@media only screen and (max-width: 600px) {
  ...;
}

/* Small devices (portrait tablets and large phones, 600px and up) */
@media only screen and (min-width: 600px) {
  ...;
}

/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {
  ...;
}

/* Large devices (laptops/desktops, 992px and up) */
@media only screen and (min-width: 992px) {
  ...;
}

/* Extra large devices (large laptops and desktops, 1200px and up) */
@media only screen and (min-width: 1200px) {
  ...;
}
```

## Orientation: Portrait / Landscape

Media queries can also be used to change layout of a page depending on the orientation of the browser.

You can have a set of CSS properties that will only apply when the browser window is wider than its height, a so called "Landscape" orientation:

```css
@media only screen and (orientation: landscape) {
  body {
    background-color: lightblue;
  }
}
```

## Hide Elements With Media Queries

Another common use of media queries, is to hide elements on different screen sizes:

```css
/* If the screen size is 600px wide or less, hide the element */
@media only screen and (max-width: 600px) {
  div.could-be-hidden {
    display: none;
  }
}
```

## sources

- https://www.w3schools.com/css/css_rwd_mediaqueries.asp
- https://dev.to/artworks_joy/learn-css-media-queries-by-building-three-projects-3a8b
