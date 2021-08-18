XRSession: visibilitychange event
=================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `visibilitychange` event is sent to an [`XRSession`](../xrsession) to inform it when it becomes visible or hidden, or when it becomes visible but not currently focused. Upon receiving the event, you can check the value of the session's [`visibilityState`](visibilitystate) property to determine the new visibility state.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../xrsessionevent"><code>XRSessionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onvisibilitychange"><code>onvisibilitychange</code></a></td></tr></tbody></table>

When the `XRSession` receives this event, the visibility state has already been changed.

Examples
--------

This example demonstrates how to listen for a `visibilitychange` event on a WebXR session, using [`addEventListener()`](../eventtarget/addeventlistener) to begin listening for the event:

    navigator.xr.requestSession("inline").then((xrSession) => {
      xrSession.addEventListener("visibilitychange", e => {
        switch(e.session.visibilityState) {
          case "visible":
          case "visible-blurred":
            mySessionVisible(true);
            break;
          case "hidden":
            mySessionVisible(false);
            break;
        }
      });
    });

When a visibility state change occurs, the event is received and dispatched to a function `mySessionVisible()`, with a Boolean parameter indicating whether or not the session is presently being displayed to the user.

You can also create the event handler by assigning it to the [`XRSession`](../xrsession)'s [`onvisibilitychange`](onvisibilitychange) event handler property, like this:

    xrSession.onvisibilitychange = (e) => {
      /* event handled here */
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#eventdef-xrsession-visibilitychange">WebXR Device API<br />
<span class="small">The definition of 'visibilitychange event' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`visibilitychange_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/visibilitychange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/visibilitychange_event</a>
