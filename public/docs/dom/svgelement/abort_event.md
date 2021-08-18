SVGElement: abort event
=======================

The `abort` event is fired when page loading is stopped before an SVG element has been allowed to load completely. This basically implements the standard `abort` DOM event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../svgevent"><code>SVGEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onabort</code></td></tr></tbody></table>

Examples
--------

    svgElem.addEventListener('abort', () => {
      console.log('Load aborted.');
    })

Specifications
--------------

Not really described anywhere specifically, but [mentioned in the SVG 2 spec](https://svgwg.org/svg2-draft/single-page.html#changes-interact).

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

`abort_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/abort_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGElement/abort_event</a>
