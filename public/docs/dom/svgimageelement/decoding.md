SVGImageElement.decoding
========================

The `decoding` property of the [`SVGImageElement`](../svgimageelement) interface represents a hint given to the browser on how it should decode the image.

Syntax
------

    var refStr = SVGImageElement.decoding
    SVGImageElement.decoding = refStr;

### Values

A [`DOMString`](../domstring) representing the decoding hint. Possible values are:

-   `sync`: Decode the image synchronously for atomic presentation with other content.
-   `async`: Decode the image asynchronously to reduce delay in presenting other content.
-   `auto`: Default mode, which indicates no preference for the decoding mode. The browser decides what is best for the user.

Examples
--------

    var img = new Image();
    img.decoding = 'sync';
    img.src = 'img/logo.svg';

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#image-decoding-hint">HTML Living Standard<br />
<span class="small">The definition of 'decoding' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`decoding`

65

≤79

63

No

52

No

65

65

63

47

No

9.0

See also
--------

-   [&lt;img&gt;: The Image Embed element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGImageElement/decoding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGImageElement/decoding</a>
