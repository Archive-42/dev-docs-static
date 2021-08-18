# Document.caretPositionFromPoint()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `caretPositionFromPoint()` property of the [`Document`](../document) interface returns a [`CaretPosition`](../caretposition) object, containing the DOM node, along with the caret and caret's character offset within that node.

## Syntax

    caretPositionFromPoint(x, y);

### Parameters

`x`  
The horizontal coordinate of a point.

`y`  
The vertical coordinate of a point.

### Returns

A [`CaretPosition`](../caretposition) object.

## Example

Click anywhere in the **Demo** paragraph below to insert a line break at the point where you click. The code for it is below the demo.

### Demo

The code below first checks for [`document.caretRangeFromPoint`](caretrangefrompoint) support, but if the browser doesn’t support that, the code then checks for `document.caretPositionFromPoint`, and uses that instead.

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

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-document-caretpositionfrompoint">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'caretPositionFromPoint()' in that specification.</span></a></td></tr></tbody></table>

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

`caretPositionFromPoint`

No

No

20

No

No

No

No

No

20

No

No

No

## See also

- [`CaretPosition`](../caretposition)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/caretPositionFromPoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/caretPositionFromPoint</a>
