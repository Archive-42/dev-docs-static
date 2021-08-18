# Document.caretRangeFromPoint()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `caretRangeFromPoint()` method of the [`Document`](../document) interface returns a [`Range`](../range) object for the document fragment under the specified coordinates.

## Syntax

    var range = document.caretRangeFromPoint(float x, float y);

### Parameters

x  
A horizontal position within the current viewport.

y  
A vertical position within the current viewport.

### Returns

One of the following:

- A [`Range`](../range).
- `Null`, if x or y are negative, outside viewport, or there is no text entry node.

## Example

Click anywhere in the **Demo** paragraph below to insert a line break at the point where you click. The code for it is below the demo.

### Demo

The code below first checks for `document.caretRangeFromPoint` support, but if the browser doesn’t support that, the code then checks for [`document.caretPositionFromPoint`](caretpositionfrompoint), and uses that instead.

### JavaScript

    function insertBreakAtPoint(e) {
      let range;
      let textNode;
      let offset;

      if (document.caretRangeFromPoint) {
        range = document.caretRangeFromPoint(e.clientX, e.clientY);
        textNode = range.startContainer;
        offset = range.startOffset;
      } else if (document.caretPositionFromPoint) {
        range = document.caretPositionFromPoint(e.clientX, e.clientY);
        textNode = range.offsetNode;
        offset = range.offset;
      } else {
        document.body.textContent = "[This browser supports neither"
          + " document.caretRangeFromPoint"
          + " nor document.caretPositionFromPoint.]";
        return;
      }
      // Only split TEXT_NODEs
      if (textNode && textNode.nodeType == 3) {
        let replacement = textNode.splitText(offset);
        let br = document.createElement('br');
        textNode.parentNode.insertBefore(br, replacement);
      }
    }

    let paragraphs = document.getElementsByTagName("p");
    for (let i = 0; i < paragraphs.length; i++) {
      paragraphs[i].addEventListener('click', insertBreakAtPoint, false);
    }

### HTML

    <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr,
    sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat,
    sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum.
    Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>

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

`caretRangeFromPoint`

4

12

No

No

15

5

≤37

18

No

14

4

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/caretRangeFromPoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/caretRangeFromPoint</a>
