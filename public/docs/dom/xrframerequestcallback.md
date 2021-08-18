XRFrameRequestCallback
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `XRFrameRequestCallback` is a callback function passed into [`XRSession.requestAnimationFrame`](xrsession/requestanimationframe) (part of [WebXR API](webxr_device_api)) to obtain the current time and the current [`XRFrame`](xrframe).

Syntax
------

    function XRFrameRequestCallback(time, XRFrame){
      // Process XRFrame here
    }
    XRSession.requestAnimationFrame(XRFrameRequestCallback)

### Parameters

[`DOMHighResTimeStamp`](domhighrestimestamp)  
A timestamp corresponding to the returned `XRFrame`.

[`XRFrame`](xrframe)  
An `XRFrame` representing a snapshot of the state of all of the tracked objects for the [`XRSession`](xrsession).

### Return Value

None.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#callbackdef-xrframerequestcallback">WebXR Device API<br />
<span class="small">The definition of 'XRFrameRequestCallback' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRFrameRequestCallback`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRFrameRequestCallback" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRFrameRequestCallback</a>
