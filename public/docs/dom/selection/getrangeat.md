Selection.getRangeAt()
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.getRangeAt()` method returns a range object representing one of the ranges currently selected.

Syntax
------

    range = sel.getRangeAt(index)

### Parameters

`index`  
The zero-based index of the range to return. A negative number or a number greater than or equal to [`Selection.rangeCount`](rangecount) will result in an error.

### Return value

The specified [`Range`](../range) object.

Example
-------

    let ranges = [];

    sel = window.getSelection();

    for(let i = 0; i < sel.rangeCount; i++) {
     ranges[i] = sel.getRangeAt(i);
    }
    /* Each item in the ranges array is now
     * a range object representing one of the
     * ranges in the current selection */

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-getrangeat">Selection API<br />
<span class="small">The definition of 'Selection: getRangeAt()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`getRangeAt`

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
-   [Tree Selection](https://developer.mozilla.org/en-US/docs/XUL_Tutorial/Tree_Selection) (for the `getRangeAt()` method on the `nsITreeSelection` interface)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/getRangeAt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/getRangeAt</a>
