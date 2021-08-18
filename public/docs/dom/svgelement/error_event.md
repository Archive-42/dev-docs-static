SVGElement: error event
=======================

The `error` event is fired when an SVG element does not load properly or when an error occurs during script execution.

This basically implements the standard `error` DOM event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../svgevent"><code>SVGEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onerror</code></td></tr></tbody></table>

Examples
--------

    svgElem.addEventListener('error', () => {
      console.log('SVG not loaded properly.');
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/single-page.html#interact-ErrorEvent">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'error' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`error_event`

?

?

?

?

?

?

?

?

?

?

?

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/error_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/error_event</a>
