XRSystem
========

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [WebXR Device API](webxr_device_api) interface `XRSystem` provides methods which let you get access to an [`XRSession`](xrsession) object representing a WebXR session. With that `XRSession` in hand, you can use it to interact with the Augmented Reality (AR) or Virtual Reality (VR) device.

Properties
----------

*While `XRSystem` directly offers no properties, it does inherit properties from its parent interface, [`EventTarget`](eventtarget).*

Methods
-------

*In addition to inheriting methods from its parent interface, [`EventTarget`](eventtarget), the `XRSystem` interface includes the following methods:*

 [`isSessionSupported()`](xrsystem/issessionsupported) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a promise which resolves to `true` if the browser supports the given [`XRSessionMode`](xrsessionmode). Resolves to `false` if the specified mode isn't supported.

 [`requestSession()`](xrsystem/requestsession) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a promise that resolves to a new [`XRSession`](xrsession) with the specified [`XRSessionMode`](xrsessionmode).

Events
------

 [`devicechange`](xrsystem/devicechange_event) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Sent when the set of available XR devices has changed.  
Also available using the [`ondevicechange`](xrsystem/ondevicechange) event handler.

Usage notes
-----------

This interface was previously known as `XR` in earlier versions of the specification; if you see references to `XR` in code or documentation, replace that with `XRSystem`.

Examples
--------

The following example shows how to use both [`isSessionSupported()`](xrsystem/issessionsupported) and [`requestSession()`](xrsystem/requestsession).

    if (navigator.xr) {
      immersiveButton.addEventListener("click", onButtonClicked);
      navigator.xr.isSessionSupported('immersive-vr')
      .then((isSupported) => {
        if (isSupported) {
          immersiveButton.disabled = false;
        } else {
          immersiveButton.disabled = true;
        }
      });
    }

    function onButtonClicked() {
      if (!xrSession) {
        navigator.xr.requestSession('immersive-vr')
        .then((session) => {
          // onSessionStarted() not shown for reasons of brevity and clarity.
          onSessionStarted(session);
        });
      } else {
        // Shut down the already running XRSession
        xrSession.end()
        .then(() => {
          // Since there are cases where the end event is not sent, call the handler here as well.
          onSessionEnded();
        });
      }
    }

This code starts by checking to see if WebXR is available by looking for the [`navigator.xr`](navigator/xr) property. If it's found, we know WebXR is present, so we proceed by establishing a handler for the button which the user can click to toggle immersive VR mode on and off.

However, we don't yet know if the desired immersive mode is available. To determine this, we call `isSessionSupported()`, passing it the desired session option before enabling the button, `immersiveButton`, which the user can then use to switch to immersive mode only if immersive VR mode is available. If immersive VR isn't available, the button is disabled to prevent its use.

The `onButtonClicked()` function checks to see if there's already a session running. If there isn't, we use `requestSession()` to start one and, once the returned promise resolves, we call a function `onSessionStarted()` to set up our session for rendering and so forth.

If, on the other hand, there is already an ongoing XR session, we instead call [`end()`](xrsession/end) to end the current session. When the current session ends, the [`end`](xrsession/end_event) event is sent, so set `xrSession` to `null` in its handler to record the fact that we no longer have an ongoing session. That way, if the user clicks the button again, a new session will start.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrsystem-interface">WebXR Device API<br />
<span class="small">The definition of 'XRSystem' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRSystem`

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

`devicechange_event`

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

`isSessionSupported`

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

`ondevicechange`

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

`requestSession`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSystem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSystem</a>
