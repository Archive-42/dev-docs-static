Selection.removeRange()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.removeRange()` method removes a range from a selection.

Syntax
------

    sel.removeRange(range)

### Parameters

*`range`*  
A range object that will be removed to the selection.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

Examples
--------

    /* Programmaticaly, more than one range can be selected.
     * This will remove all ranges except the first. */
    s = window.getSelection();
    if(s.rangeCount > 1) {
     for(var i = 1; i < s.rangeCount; i++) {
      s.removeRange(s.getRangeAt(i));
     }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-removerange">Selection API<br />
<span class="small">The definition of 'Selection.removeRange()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`removeRange`

58

12

1

9

45

≤12.1-15

No

58

58

4

43

≤12.1-14

No

7.0

See also
--------

-   [`Selection`](../selection), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/removeRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/removeRange</a>
