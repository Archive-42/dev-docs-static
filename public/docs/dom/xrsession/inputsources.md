XRSession.inputSources
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The *read-only* `inputSources` property of the [`XRSession`](../xrsession) interface returns an [`XRInputSourceArray`](../xrinputsourcearray) object which lists all controllers and input devices which are expressly associated with the XR device and are currently available. These controllers may include handheld controllers, XR-equipped gloves, optically tracked hands, and gaze-based input methods. Keyboards, gamepads, and mice are *not* considered WebXR input sources.

**Note:** Traditional gamepad controllers are supported using the [Gamepad API](../gamepad_api).

Syntax
------

    inputSources = xrSession.inputSources;

### Value

An [`XRInputSourceArray`](../xrinputsourcearray) object listing all of the currently-connected input controllers which are linked specifically to the XR device currently in use. The returned object is **live**; as devices are connected to and removed from the user's system, the list's contents update to reflect the changes.

Usage notes
-----------

You can add a handler for the `XRSession` event [`inputsourceschange`](inputsourceschange_event) to be advised when the contents of the session's connected devices list changes. You can then either get the value of `inputSources` to examine the list, or you can refer to a reference to the list that you've previously saved.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-inputsources">WebXR Device API<br />
<span class="small">The definition of 'XRSession.inputSources' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`inputSources`

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

-   [`XRInputSource`](../xrinputsource)
-   [`XRSession.oninputsourceschange`](oninputsourceschange)
-   [Gamepad API](../gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/inputSources" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/inputSources</a>
