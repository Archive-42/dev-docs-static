XRSession.onvisibilitychange
============================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `onvisibilitychange` attribute of the [`XRSession`](../xrsession) object is the event handler for the [`visibilitychange`](visibilitychange_event) event, which is dispatched when the visibility state of the XR session changes. The visibility state of the session is accessible via [`XRSession.visibilityState`](visibilitystate).

**Note:** The visibility state of XR session affects the frame loop so callbacks registered via [`XRSession.requestAnimationFrame()`](requestanimationframe) might not be called. Consult [`XRSession.visibilityState`](visibilitystate) article for details.

Syntax
------

    XRSession.onvisibilitychange = function(event) { ... }

Example
-------

    XRSession.onvisibilitychange = function(event) {
      console.log("The visibility the XR session changed.")
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-onvisibilitychange">WebXR Device API<br />
<span class="small">The definition of 'XRSession.onvisibilitychange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onvisibilitychange`

79

79

No

No

No

No

No

79

No

No

No

11.2

See also
--------

-   [`XRSession.visibilityState`](visibilitystate)
-   [`XRSession.requestAnimationFrame()`](requestanimationframe)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onvisibilitychange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onvisibilitychange</a>
