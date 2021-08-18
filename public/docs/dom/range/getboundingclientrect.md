Range.getBoundingClientRect()
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Range.getBoundingClientRect()` method returns a [`DOMRect`](../domrect) object that bounds the contents of the range; this is a rectangle enclosing the union of the bounding rectangles for all the elements in the range.

This method is useful for determining the viewport coordinates of the cursor or selection inside a text box. See [`Element.getBoundingClientRect()`](../element/getboundingclientrect) for details on the returned value.

Syntax
------

    boundingRect = range.getBoundingClientRect()

Example
-------

### HTML

    <div id="highlight"></div>
    <p>This example positions a "highlight" rectangle behind the contents of a range. The range's content <b>starts here</b> and continues on until it <b>ends here</b>. The bounding client rectangle contains everything selected in the range.</p>

### CSS

    #highlight {
      background: yellow;
      position: absolute;
      z-index: -1;
    }

    p {
      width: 200px;
    }

### JavaScript

    const range = document.createRange();
    range.setStartBefore(document.getElementsByTagName('b').item(0), 0);
    range.setEndAfter(document.getElementsByTagName('b').item(1), 0);

    const clientRect = range.getBoundingClientRect();
    const highlight = document.getElementById('highlight');
    highlight.style.left = `${clientRect.x}px`;
    highlight.style.top = `${clientRect.y}px`;
    highlight.style.width = `${clientRect.width}px`;
    highlight.style.height = `${clientRect.height}px`;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-range-getboundingclientrect">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Range.getBoundingClientRect()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`getBoundingClientRect`

4

12

4

9

≤12.1

5

≤37

18

4

≤12.1

4

1.0

See also
--------

-   [`Range.getClientRects()`](getclientrects) - finer-grained result for non-rectangular ranges (e.g., when the selection wraps onto the next line);
-   [`Element.getBoundingClientRect()`](../element/getboundingclientrect)
-   [`Document.caretPositionFromPoint()`](../document/caretpositionfrompoint) - to get the (node, offset) from viewport coordinates.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/getBoundingClientRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/getBoundingClientRect</a>
