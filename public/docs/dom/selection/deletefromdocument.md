Selection.deleteFromDocument()
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `deleteFromDocument()` method of the [`Selection`](../selection) interface deletes the selected text from the document's DOM.

Syntax
------

    sel.deleteFromDocument()

### Parameters

*None.*

Example
-------

This example lets you delete selected text by clicking a button. Upon clicking the button, the  
[`Window.getSelection()`](../window/getselection) method gets the selected text, and the `deleteFromDocument()` method removes it.

### HTML

    <p>Try highlighting some of the text in this paragraph. Once you do, you can remove the selected content by clicking the button below.</p>
    <button>Delete selected text</button>

### JavaScript

    let button = document.querySelector('button');
    button.addEventListener('click', deleteSelection);

    function deleteSelection() {
      let selection = window.getSelection();
      selection.deleteFromDocument();
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-deletefromdocument">Selection API<br />
<span class="small">The definition of 'Selection.deleteFromDocument()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`deleteFromDocument`

1

12

1

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

See also
--------

-   [`Selection`](../selection), the interface defining this method

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/deleteFromDocument" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/deleteFromDocument</a>
