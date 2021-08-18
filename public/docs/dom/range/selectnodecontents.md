Range.selectNodeContents()
==========================

The `Range.selectNodeContents()` method sets the [`Range`](../range) to contain the contents of a [`Node`](../node).

The parent `Node` of the start and end of the `Range` will be the reference node. The `startOffset` is 0, and the `endOffset` is the number of child `Node`s or number of characters contained in the reference node.

Syntax
------

    range.selectNodeContents(referenceNode);

### Parameters

`referenceNode`  
The [`Node`](../node) whose contents will be selected within a [`Range`](../range).

Example
-------

    range = document.createRange();
    referenceNode = document.getElementsByTagName("div")[0];
    range.selectNodeContents(referenceNode);

### Live sample

This example lets the user select and deselect a paragraph with buttons. [`Document.createRange()`](../document/createrange), `Range.selectNodeContents()`, and [`Selection.addRange()`](../selection/addrange) are used to select the content. [`Window.getSelection()`](../window/getselection) and [`Selection.removeAllRanges()`](../selection/removeallranges) are used to deselect it.

#### HTML

    <p id="p"><b>Use the buttons below</b> to select or deselect the contents of this paragraph.</p>
    <button id="select-button">Select paragraph</button>
    <button id="deselect-button">Deselect paragraph</button>

#### JavaScript

    const p = document.getElementById('p');
    const selectButton = document.getElementById('select-button');
    const deselectButton = document.getElementById('deselect-button');

    selectButton.addEventListener('click', e => {
      // Clear any current selection
      const selection = window.getSelection();
      selection.removeAllRanges();

      // Select paragraph
      const range = document.createRange();
      range.selectNodeContents(p);
      selection.addRange(range);
    });

    deselectButton.addEventListener('click', e => {
      const selection = window.getSelection();
      selection.removeAllRanges();
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-selectnodecontents">DOM<br />
<span class="small">The definition of 'Range.selectNodeContents()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-selectNodeContents">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.selectNodeContents()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`selectNodeContents`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/selectNodeContents" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/selectNodeContents</a>
