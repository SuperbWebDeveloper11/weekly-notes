# The Document Object Model

## Introduction

When you open a web page in your browser, the browser retrieves the page’s HTML text and parses it.
The browser builds up a model of the document’s structure and uses this model to draw the page on the screen.
You can read or modify this model and and the page on the screen is updated to reflect the changes.

## Finding elements

If we want to find a specific node in the document, reaching it by starting at document.body and following a fixed path of properties is a bad idea. Doing so bakes assumptions into our program about the precise structure of the
document—a structure you might want to change later.

Instead you can use some methods like:
**getElementsByTagName** method, which collects all elements with the given tag name,
**getElementById** method to find a specific single node by it's Id
**getElementsByClassName** method to find a nodes by their class attribute

## Changing the document

Almost everything about the DOM data structure can be changed. The shape of the document tree can be modified by changing parent-child relationships. Nodes have a remove method to remove them from their current parent node. To add a child node to an element node, we can use appendChild, which puts it at the end of the list of children, or insertBefore, which inserts the node given as the first argument before the node given as the second argument.

Example

```javascript
let paragraphs = document.body.getElementsByTagName("p");
document.body.insertBefore(paragraphs[2], paragraphs[0]);
```

## Replace img tags with text nodes contains their alt

```html
<p><img src="" alt="image 1" /></p>
<p><img src="" alt="image 2" /></p>
<p><img src="" alt="image 3" /></p>
<p><button onclick="replaceImages()">Replace</button></p>
```

```javascript
const images = document.getElementsByTagName("img");
function replaceImages() {
  Array.from(images).map((imageNode) => {
    const textNode = document.createTextNode(imageNode.alt);
    imageNode.parentElement.replaceChild(textNode, imageNode);
  });
}
```

## Event Handler

```html
      <button id="btn">Click Me</button>
      <p>Nothing will happen if you click me</p>
    </div>

```

```javascript
const btn = document.getElementById("btn");
btn.addEventListener("click", () => {
  alert("You clicked the button");
});
```

That example attaches a handler to the button node. Clicks on the button cause that handler to run, but clicks on the rest of the document do not.
Giving a node an onclick attribute has a similar effect. This works for most types of events—you can attach a handler through the attribute whose name is the event name with on in front of it.
But a node can have only one onclick attribute, so you can register only one handler per node that way. The addEventListener method allows you to add any number of handlers so that it is safe to add handlers even if there is already another handler on the element.

## Event objects

Though we have ignored it so far, event handler functions are passed an argument: the event object. This object holds additional information about the event.

```javascript
const btn = document.getElementById("btn");
btn.addEventListener("click", (event) => {
  console.log(event);
  alert("You clicked the button");
});
```

## Propagation

For most event types, handlers registered on nodes with children will also receive events that happen in the children. If a button inside a paragraph is clicked, event handlers on the paragraph will also see the click event.
But if both the paragraph and the button have a handler, the more specific handler—the one on the button—gets to go first. The event is said to propagate outward, from the node where it happened to that node’s parent node and on to the root of the document.

## Default actions

Many events have a default action associated with them. If you click a link, you will be taken to the link’s target. If you press the down arrow, the browser will scroll the page down. If you right-click, you’ll get a context menu. And so on.
For most types of events, the JavaScript event handlers are called before the default behavior takes place. If the handler doesn’t want this normal behavior to happen, typically because it has already taken care of handling the event, it can call the preventDefault method on the event object.
This can be used to implement your own keyboard shortcuts or context menu. It can also be used to obnoxiously interfere with the behavior that users expect. (For example, here is a link that cannot be followed). Try not to do such things unless you have a really good reason to. It’ll be
unpleasant for people who use your page when expected behavior is broken.

## Key events

When a key on the keyboard is pressed, your browser fires a "keydown" event. When it is released, you get a "keyup" event.

## Scroll events

The following example draws a progress bar above the document and updates it to fill up as you scroll down

```css
#progress {
  border-bottom: 2px solid blue;
  width: 0;
  position: fixed;
  top: 0;
  left: 0;
}
```

```html
<div id="progress"></div>
```

```javascript
// Create some content
document.body.appendChild(
  document.createTextNode("some content ".repeat(1000))
);
let bar = document.querySelector("#progress");
window.addEventListener("scroll", () => {
  let max = document.body.scrollHeight - innerHeight;
  bar.style.width = `${(pageYOffset / max) * 100}%`;
});
```

I stopped in **Focus events** page 254

## sources:

Eloquent JavaScript 3rd edition book By Marijn Haverbeke
