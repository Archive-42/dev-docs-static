Window.history
==============

The `Window.history` read-only property returns a reference to the [`History`](../history) object, which provides an interface for manipulating the browser *session history* (pages visited in the tab or frame that the current page is loaded in).

See [Manipulating the browser history](../history_api) for examples and details. In particular, that article explains security features of the [`pushState()`](../history/pushstate) and [`replaceState()`](../history/replacestate) methods that you should be aware of before using them.

Example
-------

    history.back();     // equivalent to clicking back button
    history.go(-1);     // equivalent to history.back();

Notes
-----

For top-level pages you can see the list of pages in the session history, accessible via the `History` object, in the browser's dropdowns next to the back and forward buttons.

For security reasons the `History` object doesn't allow the non-privileged code to access the [URLs](https://developer.mozilla.org/en-US/docs/Glossary/URL) of other pages in the session history, but it does allow it to navigate the session history.

There is no way to clear the session history or to disable the back/forward navigation from unprivileged code. The closest available solution is the [`location.replace()`](../location/replace) method, which replaces the current item of the session history with the provided URL.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#the-history-interface">HTML Living Standard<br />
<span class="small">The definition of 'The History interface' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#the-history-interface">HTML5<br />
<span class="small">The definition of 'The History interface' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`history`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/history" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/history</a>
