XRSessionEvent.session
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRSessionEvent`](../xrsessionevent) interface's `session` property indicates which [`XRSession`](../xrsession) the event is about.

Syntax
------

    xrSession = xrSessionEvent.session;

### Value

An [`XRSession`](../xrsession) object indicating which WebXR session the event refers to.

Examples
--------

In this example, the `session` property is used to obtain the session object to manage when an event is received.

    xrSession.addEventListener("visibilitychange", e => {
      switch(e.session.visibilityState) {
        case "hidden":
          myEnableRendering(true);
          break;
        case "visible":
        case "visible-blurred":
          myEnableRendering(false);
          break;
      }
    });

This calls a function that reacts to the session's visibility state change.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsessionevent-session">WebXR Device API<br />
<span class="small">The definition of 'XRSessionEvent.session' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`session`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSessionEvent/session" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSessionEvent/session</a>
