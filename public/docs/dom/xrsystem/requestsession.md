XRSystem: requestSession()
==========================

The **[`XRSystem`](../xrsystem)** interface's `requestSession()` method returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to an [`XRSession`](../xrsession) object through which you can manage the requested type of WebXR session.

While only one immersive VR session can be active at a time, multiple inline sessions can be in progress at once.

Syntax
------

    var sessionPromise = xr.requestSession(sessionMode, sessionInit)

### Parameters

`sessionMode`  
A [`DOMString`](../domstring) whose value is one of those included in the [`XRSessionMode`](../xrsessionmode) `enum`. The supported modes are:

 `immersive-ar` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The session's output will be given exclusive access to the immersive device, but the rendered content will be blended with the real-world environment. The session's [`environmentBlendMode`](../xrsession/environmentblendmode) indicates the method to be used to blend the content together.

**Important:** The `immersive-ar` mode is defined by the WebXR Augmented Reality Module, which is not yet stable and should not be used other than for testing and experimentation.

`immersive-vr`  
Indicates that the rendered session will be displayed using an immersive XR device in VR mode; it is not intended to be overlaid or integrated into the surrounding environment. The [`environmentBlendMode`](../xrsession/environmentblendmode) is expected to be `opaque` if possible, but might be `additive` if the hardware requires it.

`inline`  
The output is presented inline within the context of an element in a standard HTML document, rather than occupying the full visual space. Inline sessions can be presented in either mono or stereo mode, and may or may not have viewer tracking available. Inline sessions don't require special hardware and should be avalable on any [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) offering WebXR API support.

 `sessionInit` <span class="badge inline optional">Optional</span>   
A [`XRSessionInit`](../xrsessioninit) object providing options to configure the new [`XRSession`](../xrsession). See [Specifying session options](#specifying_session_options) for details on how to configure a WebXR session.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an [`XRSession`](../xrsession) object if the device and user agent support the requested mode and features.

### Exceptions

This method doesn't throw true exceptions; instead, it rejects the returned promise, passing into it a [`DOMException`](../domexception) whose `name` is one of the following:

`InvalidStateError`  
The requested session mode is `immersive-vr` but there is already an immersive VR session either currently active or in the process of being set up. There can only be one immersive VR session at a time.

`NotSupportedError`  
There is no WebXR-compatible device available, or the device does not support the specified `sessionMode`; this can also be thrown if any of the *required* options are unsupported.

`SecurityError`  
Permission to enter the specified XR mode is denied. This can happen for a number of reasons, which are covered in more detail in [Permissions and security](#) in [WebXR Device API](../webxr_device_api).

Examples
--------

### Creating an immersive VR session

The following example calls `requestSession()` requesting an `"immersive-vr"` session. If the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolves, it sets up a session and initiates the animation loop.

    navigator.xr.requestSession("immersive-vr")
    .then((xrSession) => {
      xrSession.addEventListener('end', onXRSessionEnded);
      // Do necessary session setup here.
      // Begin the session’s animation loop.
      xrSession.requestAnimationFrame(onXRAnimationFrame);
    }).catch(function(error) {
      // "immersive-vr" sessions are not supported
      console.warn("'immersive-vr' isn't supported, or an error occurred activating VR!");
    });

### Verifying WebXR support and using a button to start VR mode

The following example shows how to use both `isSessionSupported()` and `requestSession()`. First, it checks to see if WebXR is available by verifying the existence of [`navigator.xr`](../navigator/xr). Next, it calls `isSessionSupported()`, passing it the desired session option before enabling controls for entering XR. Adding controls is a necessary step because entering XR requires a user action. Finally, the `onButtonClicked()` method calls `requestSession()` using the same session option passed to `isSessionSupported()`.

    if (navigator.xr) {
      navigator.xr.isSessionSupported('immersive-vr')
      .then((isSupported) => {
        if (isSupported) {
          immersiveButton.addEventListener('click', onButtonClicked);
          immersiveButton.textContent = 'Enter XR';
          immersiveButton.disabled = false;
        } else {
          console.log("WebXR doesn't support immersive-vr mode!");
        }
      });
    } else {
      console.log("WebXR is not available!");
    }

    function onButtonClicked() {
      if (!xrSession) {
        navigator.xr.requestSession('immersive-vr')
        .then((session) => {
          xrSession = session;
          // onSessionStarted() not shown for reasons of brevity and clarity.
          onSessionStarted(xrSession);
        });
      } else {
        // Button is a toggle button.
        xrSession.end().then(() => xrSession = null);
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsystem-requestsession">WebXR Device API<br />
<span class="small">The definition of 'requestSession()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSystem/requestSession" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSystem/requestSession</a>
