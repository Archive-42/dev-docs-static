XRSession.onselectstart
=======================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `onselectstart` attribute of the [`XRSession`](../xrsession) object is the event handler for the [`selectstart`](selectstart_event) event, which is dispatched when user starts making some sort of selection by pressing a trigger, touchpad, or button, speaking a command, or making a hand gesture. For example, this might include pressing a button or moving a joystick.

**Note:** Not to be confused with [`XRSession.onselect`](onselect) and [`XRSession.onselectend`](onselectend).

Syntax
------

    XRSession.onselectstart = function(event) { ... }

Example
-------

    XRSession.onselectstart = function(event) {
      console.log("The user has started a primary action, but might not have completed it.")
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-onselectstart">WebXR Device API<br />
<span class="small">The definition of 'XRSession.onselectstart' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onselectstart`

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

-   [`XRSession.onselectend`](onselectend)
-   [`XRSession.onselect`](onselect)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onselectstart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/onselectstart</a>
