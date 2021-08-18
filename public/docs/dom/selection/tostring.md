Selection.toString()
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.toString()` method returns a string currently being represented by the selection object, i.e. the currently selected text.

Syntax
------

    sel.toString()

### Return value

A string representing the selection.

Description
-----------

This method returns the currently selected text.

In [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript), this method is called automatically when a function the selection object is passed to requires a string:

    alert(window.getSelection()) // What is called
    alert(window.getSelection().toString())  // What is actually being effectively called.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-stringifier">Selection API<br />
<span class="small">The definition of 'Selection stringifier' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`toString`

1

≤18

1

9

≤12.1

Yes

1

18

4

≤12.1

Yes

1.0

See also
--------

-   [`Selection`](../selection), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/toString</a>
