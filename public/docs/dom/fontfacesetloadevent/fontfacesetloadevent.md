FontFaceSetLoadEvent.FontFaceSetLoadEvent()
===========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `FontFaceSetLoadEvent` constructor creates a new <span class="page-not-created">`FontFaceLoadEvent`</span> object which is fired whenever a [`FontFaceSet`](../fontfaceset) loads.

Syntax
------

    var fontFaceSetLoadEvent = new FontFaceSetLoadEvent(type[, options])

### Parameters

*type*  
The literal value `'Type'` (quotation marks included).

 *options* <span class="badge inline optional">Optional</span>   
Options are as follows:

-   `fontfaces`: An array of [`FontFace`](../fontface) instances.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#dom-fontfacesetloadevent-fontfacesetloadevent">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'FontFaceSetLoadEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`FontFaceSetLoadEvent`

57

≤79

?

No

44

No

No

57

?

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSetLoadEvent/FontFaceSetLoadEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSetLoadEvent/FontFaceSetLoadEvent</a>
