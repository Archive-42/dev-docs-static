Selection.rangeCount
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.rangeCount` read-only property returns the number of ranges in the selection.

Before the user has clicked a freshly loaded page, the `rangeCount` is `0`. After the user clicks on the page, `rangeCount` is `1`, even if no selection is visible.

A user can normally only select one range at a time, so the `rangeCount` will usually be `1`. Scripting can be used to make the selection contain more than one range.

Gecko browsers allow multiple selections across table cells. Firefox allows to select multiple ranges in the document by using Ctrl+click (unless the click occurs within an element that has the `display: table-cell` CSS property assigned).

Syntax
------

    value = sel.rangeCount

Example
-------

The following example will show the `rangeCount` every second. Select text in the browser to see it change.

### HTML

    <table>
      <tr><td>a.1<td>a.2
      <tr><td>b.1<td>b.2
      <tr><td>c.1<td>c.2

### JavaScript

    window.setInterval(function () {
      console.log(window.getSelection().rangeCount);
    }, 1000);

### Result

Open your console to see how many ranges are in the selection. In Gecko browsers, you can select multiple ranges across table cells by holding down Ctrl while dragging with the mouse.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-rangecount">Selection API<br />
<span class="small">The definition of 'Selection.rangeCount' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`rangeCount`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   [`Selection`](../selection), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/rangeCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/rangeCount</a>
