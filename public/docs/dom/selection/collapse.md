Selection.collapse()
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.collapse()` method collapses the current selection to a single point. The document is not modified. If the content is focused and editable, the caret will blink there.

Syntax
------

    sel.collapse(node, offset);

### Parameters

*`node`*  
The caret location will be within this node. This value can also be set to `null` — if `null` is specified, the method will behave like [`Selection.removeAllRanges()`](removeallranges), i.e. all ranges will be removed from the selection.

 *`offset`* <span class="badge inline optional">Optional</span>   
The offset in `node` to which the selection will be collapsed. If not specified, the default value `0` is used.

Examples
--------

    /* Place the caret at the beginning of an HTML document's body. */
    var body = document.getElementsByTagName("body")[0];
    window.getSelection().collapse(body,0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-collapse">Selection API<br />
<span class="small">The definition of 'Selection.collapse()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`collapse`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

See also
--------

-   [`Selection`](../selection), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/collapse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/collapse</a>
