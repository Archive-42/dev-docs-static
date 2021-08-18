XRSystem: isSessionSupported()
==============================

The [`XRSystem`](../xrsystem) method `isSessionSupported()` returns a promise which resolves to `true` if the specified WebXR session mode is supported by the user's WebXR device. Otherwise, the promise resolves with `false`.

If the no devices are available or the browser doesn't have permission to use the XR device, the promise is rejected with an appropriate [`DOMException`](../domexception).

Syntax
------

    var isSupportedPromise = xr.isSessionSupported(xrSessionMode)

### Parameters

`xrSessionMode`  
A [`DOMString`](../domstring) specifying the WebXR session mode for which support is to be checked. This string must be one of `inline` (to present the WebXR content inline within the context of an HTML document) or `immersive-vr` for a fully-immersive virtual experience.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true` if the specified session mode is supported; otherwise the promise resolves to `false`.

### Exceptions

Rather than throwing true exceptions, `isSessionSupported()` rejects the returned promise, passing to the rejection handler a [`DOMException`](../domexception) whose `name` is one of the following strings.

`SecurityError`  
The document's origin does not have permission to use the `xr-spatial-tracking` [feature policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy).

Examples
--------

In this example, we see `isSessionSupported()` used to detect whether or not the device supports VR mode by checking to see if an `immersive-vr` session is supported. If it is, we set up a button to read "Enter XR", to call a method `onButtonClicked()`, and enable the button.

If no session is already underway, we request the VR session and, if successful, set up the session in a method called `onSessionStarted()`, not shown. If a session *is* already underway when the button is clicked, we call the `xrSession` object's [`end()`](../xrsession/end) method to shut down the WebXR session.

    if (navigator.xr) {
      navigator.xr.isSessionSupported('immersive-vr')
      .then((isSupported) => {
        if (isSupported) {
          userButton.addEventListener('click', onButtonClicked);
          userButton.textContent = 'Enter XR';
          userButton.disabled = false;
        }
      });
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
        xrSession.end();
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsystem-issessionsupported">WebXR Device API<br />
<span class="small">The definition of 'isSessionSupported()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSystem/isSessionSupported" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSystem/isSessionSupported</a>
