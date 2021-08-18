FontFaceSet.ready
=================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `ready` readonly property of the [`FontFaceSet`](../fontfaceset) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the given [`FontFaceSet`](../fontfaceset).

Syntax
------

    fontFaceSet.ready.then(function(fontFaceSet) {
      // ...
    });

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the given [`FontFaceSet`](../fontfaceset).

### Parameters

None.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#dom-fontfaceset-ready">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'FontFaceSet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`ready`

35

≤79

41

No

35

10

37

35

41

35

Yes

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet/ready" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet/ready</a>
