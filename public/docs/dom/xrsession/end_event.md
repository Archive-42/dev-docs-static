XRSession: end event
====================

An `end` event is fired at an [`XRSession`](../xrsession) object when the WebXR session has ended, either because the web application has chosen to stop the session, or because the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) terminated the session.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../xrsessionevent"><code>XRSessionEvent</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="onend"><code>XRSession.onend</code></a></td></tr></tbody></table>

Example
-------

To be informed when a WebXR session comes to an end, you can add a handler to your [`XRSession`](../xrsession) instance using [`addEventListener()`](../eventtarget/addeventlistener), like this:

    XRSession.addEventListener("end", function(event) {
      /* the session has shut down */
    });

Alternatively, you can use the [`XRSession.onend`](onend) event handler property to establish a handler for the `end` event:

    XRSession.onend = function(event) {
     /* the session has shut down */
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#eventdef-xrsession-end">WebXR Device API<br />
<span class="small">The definition of 'end event' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`end_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/end_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/end_event</a>
