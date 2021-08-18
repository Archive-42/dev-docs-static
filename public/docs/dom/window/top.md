Window.top
==========

Returns a reference to the topmost window in the window hierarchy.

Syntax
------

    var topWindow = window.top;

Notes
-----

Where the [`window.parent`](parent) property returns the immediate parent of the current window, `window.top` returns the topmost window in the hierarchy of window objects.

This property is especially useful when you are dealing with a window that is in a subframe of a parent or parents, and you want to get to the top-level frameset.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#dom-top">HTML Living Standard<br />
<span class="small">The definition of 'window.top' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-top">HTML5<br />
<span class="small">The definition of 'window.top' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`top`

1

12

1

Starting in Firefox 6, this property is read only, as defined by the standard.

4

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/top" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/top</a>
