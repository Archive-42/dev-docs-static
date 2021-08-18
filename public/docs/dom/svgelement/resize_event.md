SVGElement: resize event
========================

The `resize` event is fired when an SVG document is being resized. This event is only applicable to outermost SVG elements and is dispatched after the resize operation has taken place.

This basically implements the standard `resize` DOM event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../svgevent"><code>SVGEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onresize</code></td></tr></tbody></table>

Examples
--------

    svgElem.addEventListener('resize', () => {
      console.log('SVG resized.');
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/single-page.html#changes-interact">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'event changes in SVG2' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`resize_event`

Yes

≤79

Yes

?

Yes

?

Yes

Yes

Yes

Yes

?

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/resize_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/resize_event</a>
