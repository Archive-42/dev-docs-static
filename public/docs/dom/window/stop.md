Window.stop()
=============

The `window.stop()` stops further resource loading in the current browsing context, equivalent to the stop button in the browser.

Because of how scripts are executed, this method cannot interrupt its parent document's loading, but it will stop its images, new windows, and other still-loading objects.

Syntax
------

    window.stop()

Example
-------

    window.stop();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#dom-window-stop">HTML Living Standard<br />
<span class="small">The definition of 'Window.stop()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-window-stop">HTML5<br />
<span class="small">The definition of 'Window.stop' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`stop`

1

14

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/stop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/stop</a>
