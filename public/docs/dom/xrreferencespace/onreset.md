XRReferenceSpace.onreset
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Draft**

This page is not complete.

The [`XRReferenceSpace`](../xrreferencespace) interface's `onreset` event handler property can be set to a function which is called when the `XRReferenceSpace` receives a [`reset`](reset_event) event, signaling that the XR device has experienced a discontinuity large enough to require that the position and/or orientation of the origin be significantly altered to compensate.

Syntax
------

    xrReferenceSpace.onreset = eventHandler;

    eventHandler = xrReferenceSpace.onreset;

### Value

An event handler function which will be called whenever the `reset` event is received by the `XRReferenceSpace`.

Usage notes
-----------

See the [`reset`](reset_event) event documentation for further details.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrreferencespace-onreset">WebXR Device API<br />
<span class="small">The definition of 'onreset' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onreset`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpace/onreset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpace/onreset</a>
