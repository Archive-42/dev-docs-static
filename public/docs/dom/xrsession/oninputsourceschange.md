XRSession.oninputsourceschange
==============================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `oninputsourcechange` attribute of the [`XRSession`](../xrsession) object is the event handler for the <span class="page-not-created">`inputsourcechange`</span> event, which is dispatched when session's list of active XR input sources has changed. The list itself is accessible via [`XRSession.inputSources`](inputsources).

**Note:** The [`XRInputSource`](../xrinputsource) objects in [`XRSession.inputSources`](inputsources) array are "live", so values within them are updated in-place. Therefore if you wish to compare input states between frames, you should make a copy of the content of the state in question.

Syntax
------

    XRSession.oninputsourceschange = function(event) { ... }

Example
-------

    XRSession.oninputsourceschange = function(event) {
      console.log("The list of active XR input sources has changed.")
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-oninputsourceschange">WebXR Device API<br />
<span class="small">The definition of 'XRSession.oninputsourceschange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`oninputsourceschange`

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

[`XRSession.inputSources`](inputsources)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/oninputsourceschange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/oninputsourceschange</a>
