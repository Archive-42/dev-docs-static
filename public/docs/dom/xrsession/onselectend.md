XRSession.onselectend
=====================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `onselectend` attribute of the [`XRSession`](../xrsession) object is the event handler for the [`selectend`](selectend_event) event, which is dispatched when user finishes making some sort of selection by releasing a trigger, touchpad, or button, finishes speaking a command, or makes a hand gesture. For example, this might include releasing a button or joystick.

**Note:** Not to be confused with [`XRSession.onselectstart`](onselectstart) and [`XRSession.onselect`](onselect).

Syntax
------

    XRSession.onselectend = function(event) { ... }

Example
-------

    XRSession.onselectend = function(event) {
      console.log("The user has completed a primary action.")
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-onselectend">WebXR Device API<br />
<span class="small">The definition of 'XRSession.onselectend' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onselectend`

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

-   [`XRSession.onselectstart`](onselectstart)
-   [`XRSession.onselect`](onselect)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onselectend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onselectend</a>
