SVGElement: scroll event
========================

The `scroll` event is fired when an SVG document view is being shifted along the X and/or Y axes. This basically implements the standard `scroll` DOM event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../svgevent"><code>SVGEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onscroll</code></td></tr></tbody></table>

Examples
--------

    svgElem.addEventListener('scroll', () => {
      console.log('SVG scrolled.');
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

`scroll_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/scroll_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/scroll_event</a>
