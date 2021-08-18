Range.setStart()
================

The `Range.setStart()` method sets the start position of a [`Range`](../range).

If the `startNode` is a [`Node`](../node) of type [`Text`](../text), [`Comment`](../comment), or [`CDataSection`](../cdatasection), then `startOffset` is the number of characters from the start of `startNode`. For other `Node` types, `startOffset` is the number of child nodes between the start of the `startNode`.

Setting the start point below (lower in the document) the end point will result in a collapsed range with the start and end points both set to the specified start position.

Syntax
------

    range.setStart(startNode, startOffset);

### Parameters

*startNode*  
The [`Node`](../node) where the [`Range`](../range) should start.

*startOffset*  
An integer greater than or equal to zero representing the offset for the start of the [`Range`](../range) from the start of `startNode`.

Examples
--------

### Highlight part of an element

This example uses the `Range.setStart()` and [`Range.setEnd()`](setend) methods to add part of an address to a range. The selected range is then highlighted using [`Range.surroundContents()`](surroundcontents).

The address contains nine nodes: five text nodes, and four [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br) elements.

#### HTML

    <p id="address">Wyatt Earp<br>
    101 E. Main St.<br>
    Dodge City, KS<br>
    67801<br>
    USA</p>

    <hr>
    <p>Nodes in the original address:</p>
    <ol id="log"></ol>

#### JavaScript

    const address = document.getElementById('address');
    const log = document.getElementById('log');

    // Log info
    address.childNodes.forEach(node => {
      const li = document.createElement('li');
      li.textContent = `${node.nodeName}, ${node.nodeValue}`;
      log.appendChild(li);
    });

    // Highlight the street and city
    const startOffset = 2;  // Start at third node: 101 E. Main St.
    const endOffset = 5;    // End at fifth node: Dodge City, KS
    const range = document.createRange();
    range.setStart(address, startOffset);
    range.setEnd(address, endOffset);

    const mark = document.createElement('mark');
    range.surroundContents(mark);

#### Result

### Get characters from a text node

This example uses the `Range.setStart()` and [`Range.setEnd()`](setend) methods to define the contents of a range. The resulting range contains the first through fifth characters within a text node.

#### HTML

    <p id="content">0123456789</p>
    <p id="log"></p>

#### JavaScript

    const element = document.getElementById('content');
    const textNode = element.childNodes[0];
    const range = document.createRange();
    range.setStart(textNode, 0);  // Start at first character
    range.setEnd(textNode, 5);    // End at fifth character
    document.getElementById('log').textContent = range;

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-setstart">DOM<br />
<span class="small">The definition of 'Range.setStart()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-setStart">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.setStart()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`setStart`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

See also
--------

-   [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/setStart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/setStart</a>
