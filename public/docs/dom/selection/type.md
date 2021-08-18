Selection.type
==============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `type` read-only property of the [`Selection`](../selection) interface returns a [`DOMString`](../domstring) describing the type of the current selection.

Syntax
------

    value = sel.type

### Value

A [`DOMString`](../domstring) describing the type of the current selection. Possible values are:

-   `None`: No selection has currently been made.
-   `Caret`: The selection is collapsed (i.e. the caret is placed on some text, but no range has been selected).
-   `Range`: A range has been selected.

Example
-------

In this example, the event handler will fire each time a new selection is made. `console.log(selection.type)` will return `Caret` or `Range` depending on whether the caret is placed at a single point in the text, or a range has been selected.

    var selection;

    document.onselectionchange = function() {
      console.log('New selection made');
      selection = document.getSelection();
      console.log(selection.type);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-type">Selection API<br />
<span class="small">The definition of 'Selection.type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`type`

1

12

57

No

15

1.3

1

18

57

14

1

1.0

See also
--------

-   [`Selection`](../selection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/type</a>
