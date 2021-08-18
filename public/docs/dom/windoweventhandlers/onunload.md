WindowEventHandlers.onunload
============================

The `onunload` property of the [`WindowEventHandlers`](../windoweventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `unload` events. These events fire when the window is unloading its content and resources. The resource removal is processed *after* the `unload` event occurs.

**Note:** Browsers equipped with pop-up blockers will ignore all [`Window.open()`](../window/open) method calls in `onunload` event handler functions.

The `onunload` (and the `unload` event itself) are not the right features to use with `sendBeacon()`. Instead for `sendBeacon(),` use the `visibilitychange` and `pagehide` events. See discussion comments in the blog post [Beacon API is broken](https://volument.com/blog/sendbeacon-is-broken#comments).

Syntax
------

    window.addEventListener("unload", function(event) { ... });
    window.onunload = function(event) { ... };

Typically, it is better to use [`window.addEventListener()`](../eventtarget/addeventlistener) and the `unload` event, instead of `onunload`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-window-onunload">HTML Living Standard<br />
<span class="small">The definition of 'onunload' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/#windoweventhandlers">HTML 5.1<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/#windoweventhandlers">HTML5<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`onunload`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

In Firefox 1.5, using this event handler in your page prevents the browser from caching the page in the in-memory bfcache. See [Using Firefox 1.5 caching](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/1.5/Using_Firefox_1.5_caching) for details.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onunload" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onunload</a>
