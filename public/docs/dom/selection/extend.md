Selection.extend()
==================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.extend()` method moves the focus of the selection to a specified point. The anchor of the selection does not move. The selection will be from the anchor to the new focus, regardless of direction.

Syntax
------

    sel.extend(node, offset)

### Parameters

`node`  
The node within which the focus will be moved.

 `offset` <span class="badge inline optional">Optional</span>   
The offset position within `node` where the focus will be moved to. If not specified, the default value `0` is used.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-extend">Selection API<br />
<span class="small">The definition of 'Selection.extend()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`extend`

1

12

1

No

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`offset`

Yes

≤79

55

No

Yes

Yes

No

Yes

55

Yes

Yes

Yes

See also
--------

-   [`Selection`](../selection), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/extend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/extend</a>
