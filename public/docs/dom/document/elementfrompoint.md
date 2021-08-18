# Document.elementFromPoint()

The `elementFromPoint()` method, available on the [`Document`](../document) object, returns the topmost [`Element`](../element) at the specified coordinates (relative to the viewport).

If the element at the specified point belongs to another document (for example, the document of an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)), that document's parent element is returned (the `<iframe>` itself). If the element at the given point is anonymous or XBL generated content, such as a textbox's scroll bars, then the first non-anonymous ancestor element (for example, the textbox) is returned.

Elements with [`pointer-events`](https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events) set to `none` will be ignored, and the element below it will be returned.

If the method is run on another document (like an `<iframe>`'s subdocument), the coordinates are relative to the document where the method is being called.

If the specified point is outside the visible bounds of the document or either coordinate is negative, the result is `null`.

If you need to find the specific position inside the element, use [`Document.caretPositionFromPoint()`](caretpositionfrompoint).

## Syntax

    elementFromPoint(x, y)

### Parameters

`x`  
The horizontal coordinate of a point, relative to the left edge of the current [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport).

`y`  
The vertical coordinate of a point, relative to the top edge of the current viewport.

### Return value

The topmost [`Element`](../element) object located at the specified coordinates.

## Example

This example creates two buttons which let you set the current color of the paragraph element located under the coordinates `(2, 2)`.

### JavaScript

    function changeColor(newColor) {
      elem = document.elementFromPoint(2, 2);
      elem.style.color = newColor;
    }

The `changeColor()` method obtains the element located at the specified point, then sets that element's current foreground [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) property to the color specified by the `newColor` parameter.

### HTML

    <p id="para1">Some text here</p>
    <button onclick="changeColor('blue');">Blue</button>
    <button onclick="changeColor('red');">Red</button>

The HTML provides the paragraph whose color will be affected, as well as two buttons: one to change the color to blue, and another to change the color to red.

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-document-elementfrompoint">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'elementFromPoint()' in that specification.</span></a></td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`elementFromPoint`

1

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

12

3

4

≤12.1

Before Opera 53, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

4

1

Before WebView 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

18

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

4

≤12.1

Before Opera Android 47, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

3.2

1.0

Before Samsung Internet 9.0, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

## See also

- [`Document.elementsFromPoint()`](elementsfrompoint)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/elementFromPoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/elementFromPoint</a>
