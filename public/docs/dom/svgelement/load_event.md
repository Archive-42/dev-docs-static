SVGElement: load event
======================

The `load` event fires on an `SVGElement` when it is loaded in the browser, e.g. in the DOM in the case of an embedded `<svg>`. It is basically the same as the standard `load` DOM event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../svgevent"><code>SVGEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onload</code></td></tr></tbody></table>

Examples
--------

    svgElem.addEventListener('load', () => {
      console.log('SVG loaded.');
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/single-page.html#interact-LoadEvent">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'load' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`load_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/load_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/load_event</a>
