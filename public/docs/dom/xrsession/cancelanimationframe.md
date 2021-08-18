XRSession.cancelAnimationFrame()
================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `cancelAnimationFrame()` method of the [`XRSession`](../xrsession) interface cancels an animation frame which was previously requested by calling [`requestAnimationFrame`](requestanimationframe).

Syntax
------

    xrSession.cancelAnimationFrame(handle);

### Parameters

`handle`  
The unique value returned by the call to [`requestAnimationFrame()`](requestanimationframe) that previously scheduled the animation callback.

### Return value

None.

Usage notes
-----------

This function has no effect if the specified `handle` cannot be found.

Example
-------

In the example below we see code which starts up a WebXR session if immersive VR mode is supported. Once started, the session schedules its first frame to be rendered by calling [`requestAnimationFrame()`](requestanimationframe).

The `pauseXR()` function shown at the bottom can be called to suspend the WebVR session, in essence, by canceling any pending animation frame callback. Since each frame callback schedules the next one, removing the callback terminates updating of the WebXR scene.

    const XR = navigator.xr;

    let requestHandle = null;
    let xrSession = null;

    if (XR) {
      XR.isSessionSupported('immersive-vr')
      .then((isSupported) => {
        if (isSupported) {
          startXR();
        }
      });
    }

    function frameCallback(time, xrFrame) {
      xrSession.requestAnimationFrame(frameCallback);

      // Update and render the frame
    }

    async function startXR() {
      xrSession = XR.requestSession("immersive-vr");

      if (xrSession) {
        stopButton.onclick = stopXR;
        requestHandle = xrSession.requestAnimationFrame(frameCallback);
      }
    }

    function pauseXR() {
      if (xrSession && requestHandle) {
        xrSession.cancelAnimationFrame(requestHandle);
        requestHandle = null;
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-cancelanimationframe">WebXR Device API<br />
<span class="small">The definition of 'XRSession.cancelAnimationFrame' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`cancelAnimationFrame`

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

-   [`Window.cancelAnimationFrame`](../window/cancelanimationframe)
-   [`XRSession.requestAnimationFrame`](requestanimationframe)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/cancelAnimationFrame" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/cancelAnimationFrame</a>
