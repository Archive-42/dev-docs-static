SVGElement: unload event
========================

The `unload` event is fired when the DOM implementation removes an SVG document from a window or frame.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../svgevent"><code>SVGEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onunload</code></td></tr></tbody></table>

Examples
--------

    svgElem.addEventListener('unload', () => {
      console.log('SVG unloaded.');
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/single-page.html#interact-UnloadEvent">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'unload' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`unload_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/unload_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/unload_event</a>
