XRSessionMode
=============

The [WebXR Device API's](webxr_device_api) `XRSessionMode` enumerated type defines the string values used to identify the possible kinds of session mode that can be used.

Values
------

 `immersive-ar` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The session's output will be given exclusive access to the immersive device, but the rendered content will be blended with the real-world environment. The session's [`environmentBlendMode`](xrsession/environmentblendmode) indicates the method to be used to blend the content together.

**Important:** The `immersive-ar` mode is defined by the WebXR Augmented Reality Module, which is not yet stable and should not be used other than for testing and experimentation.

`immersive-vr`  
Indicates that the rendered session will be displayed using an immersive XR device in VR mode; it is not intended to be overlaid or integrated into the surrounding environment. The [`environmentBlendMode`](xrsession/environmentblendmode) is expected to be `opaque` if possible, but might be `additive` if the hardware requires it.

`inline`  
The output is presented inline within the context of an element in a standard HTML document, rather than occupying the full visual space. Inline sessions can be presented in either mono or stereo mode, and may or may not have viewer tracking available. Inline sessions don't require special hardware and should be avalable on any [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) offering WebXR API support.

Usage notes
-----------

The `XRSessionMode` type indicates the values that can be specified when calling [`XRSystem.isSessionSupported()`](xrsystem/issessionsupported) to determine whether or not the specified session type is supported and available to be used, and by [`requestSession()`](xrsystem/requestsession) to attempt to open a new WebXR session.

The `immersive-ar` mode supports all the same features and reference spaces that `immersive-vr` does, since both are immersive sessions. Browsers may support either or both of these modes, but if WebXR is available, the `inline` mode is *always* supported.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrsessionmode-enum">WebXR Device API<br />
<span class="small">The definition of 'XRSessionMode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://immersive-web.github.io/webxr-ar-module/#dom-xrsessionmode-immersive-ar">WebXR Augmented Reality Module<br />
<span class="small">The definition of 'XRSessionMode: immersive-ar' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>The <code>immersive-ar</code> value added</td></tr></tbody></table>

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

`XRSessionMode`

79

79

No

No

No

No

79

79

No

No

No

11.2

`immersive-ar`

81

81

No

No

No

No

?

81

No

No

No

12.1

`immersive-vr`

79

79

No

No

No

No

79

79

No

No

No

11.2

`inline`

79

79

No

No

No

No

79

79

No

No

No

11.2

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSessionMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSessionMode</a>
