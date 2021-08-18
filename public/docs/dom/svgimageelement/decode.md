SVGImageElement.decode
======================

The `decode()` method of the [`SVGImageElement`](../svgimageelement) interface initiates asynchronous decoding of an image, returning a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves once the image data is ready for use.

Syntax
------

    var promise = svgImageElement.decode();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves once the image data is ready to be used, such as by appending it to the DOM, replacing an existing image, and so forth.

### Exceptions

None.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/">Scalable Vector Graphics (SVG) 2</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-decode">HTML Living Standard<br />
<span class="small">The definition of 'decode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`decode`

65

≤79

No

No

52

No

65

65

No

47

No

9.0

See also
--------

-   [`HTMLImageElement.decode()`](../htmlimageelement/decode): The same thing, but for HTML [`<image>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/image) elements

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGImageElement/decode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGImageElement/decode</a>
