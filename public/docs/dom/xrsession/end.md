XRSession.end()
===============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `end()` method shuts down the [`XRSession`](../xrsession) on which it's called, returning a promise which resolves once the session has fully shut down.

Syntax
------

    xrSession.end();

### Parameters

None.

### Return value

A [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves without a value after any platform-specific steps related to shutting down the session have completed. You can use the promise to do things like update UI elements to reflect the shut down connection, trigger application shut down, or whatever else you might need to do.

Example
-------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-end">WebXR Device API<br />
<span class="small">The definition of 'XRSession.end' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`end`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/end" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/end</a>
