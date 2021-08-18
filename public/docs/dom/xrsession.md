XRSession
=========

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Draft**

This page is not complete.

The WebXR Device API's `XRSession` interface represents an ongoing XR session, providing methods and properties used to interact with and control the session. To open a WebXR session, use the [`XRSystem`](xrsystem) interface's [`requestSession()`](xrsystem/requestsession) method.

With `XRSession` methods, you can poll the viewer's position and orientation (the [`XRViewerPose`](xrviewerpose)), gather information about the user's environment, and present imagery to the user. `XRSession` supports both inline and immersive virtual and augmented reality modes.

Properties
----------

*In addition to the properties listed below, `XRSession` inherits properties from its parent interface, [`EventTarget`](eventtarget).*

 [`environmentBlendMode`](xrsession/environmentblendmode) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>   
Returns this session's blend mode which denotes how much of the real-world environment is visible through the XR device and how the device will blend the device imagery with it.

**Note:** `environmentBlendMode()` is part of the [WebXR Augmented Reality Module](https://immersive-web.github.io/webxr-ar-module), which has not been completed.

 [`inputSources`](xrsession/inputsources) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a list of this session's [`XRInputSource`](xrinputsource)s, each representing an input device used to control the camera and/or scene.

 [`renderState`](xrsession/renderstate) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
An [`XRRenderState`](xrrenderstate) object which contains options affecting how the imagery is rendered. This includes things such as the near and far clipping planes (distances defining how close and how far away objects can be and still get rendered), as well as field of view information.

 [`visibilityState`](xrsession/visibilitystate) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) whose value is one of those found in the [`XRVisibilityState`](xrvisibilitystate) enumerated type, indicating whether or not the session's imagery is visible to the user, and if so, if it's being visible but not currently the target for user events.

Methods
-------

*`XRSession` provides the following methods in addition to those inherited from its parent interface, [`EventTarget`](eventtarget).*

[`cancelAnimationFrame()`](xrsession/cancelanimationframe)  
Removes a callback from the animation frame painting callback from `XRSession`'s set of animation frame rendering callbacks, given the identifying handle returned by a previous call to [`requestAnimationFrame()`](xrsession/requestanimationframe).

[`end()`](xrsession/end)  
Ends the WebXR session. Returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves when the session has been shut down.

[`requestAnimationFrame()`](xrsession/requestanimationframe)  
Schedules the specified method to be called the next time the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) is working on rendering an animation frame for the WebXR device. Returns an integer value which can be used to identify the request for the purposes of canceling the callback using `cancelAnimationFrame()`. This method is comparable to the [`Window.requestAnimationFrame()`](window/requestanimationframe) method.

[`requestReferenceSpace()`](xrsession/requestreferencespace)  
Requests that a new [`XRReferenceSpace`](xrreferencespace) of the specified type be created. Returns a promise which resolves with the `XRReferenceSpace` or [`XRBoundedReferenceSpace`](xrboundedreferencespace) which was requested, or throws a `NotSupportedError` if the requested space type isn't supported by the device.

[`updateRenderState()`](xrsession/updaterenderstate)  
Updates the properties of the session's render state to match the values specified in the specified [`XRRenderStateInit`](xrrenderstateinit) dictionary. Any properties not included in the given dictionary are left unchanged from their current values.

Events
------

*The following events are delivered to `XRSession` objects.*

<table><thead><tr class="header"><th>Event</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><a href="xrsession/end_event"><code>end</code></a></td><td>Sent to the <code>XRSession</code> object after the WebXR session has ended and all hardware-related functions have completed. The event is represented by an object of type <a href="xrsessionevent"><code>XRSessionEvent</code></a>.<br />
Also available through the <a href="xrsession/onend"><code>onend</code></a> event handler property.</td></tr><tr class="even"><td><a href="xrsession/inputsourceschange_event"><code>inputsourceschange</code></a></td><td>An event of type <a href="xrinputsourceschangeevent"><code>XRInputSourcesChangeEvent</code></a> sent to the <code>XRSession</code> when the list of active XR input sources has changed.<br />
Also available through the <a href="xrsession/oninputsourceschange"><code>oninputsourceschange</code></a> event handler property.</td></tr><tr class="odd"><td><a href="xrsession/select_event"><code>select</code></a></td><td>An event of type <a href="xrinputsourceevent"><code>XRInputSourceEvent</code></a> which is sent to the session when one of the session's input sources has successfully completed a <a href="webxr_device_api/inputs#primary_actions">primary action</a>. This generally corresponds to the user pressing a trigger, touchpad, or button, speaks a command, or performs a recognizable gesture. The <code>select</code> event is sent after the <code>selectstart</code> event is sent and immediately before the <code>selectend</code> event is sent. If <code>select</code> is <em>not</em> sent, then the select action was aborted before being completed.<br />
Also available through the <a href="xrsession/onselect"><code>onselect</code></a> event handler property.</td></tr><tr class="even"><td><a href="xrsession/selectend_event"><code>selectend</code></a></td><td>An event of type <a href="xrinputsourceevent"><code>XRInputSourceEvent</code></a> which gets sent to the session object when one of its input devices finishes its primary action or gets disconnected while in the process of handling a primary action. For example: for button or trigger actions, this means the button has been released; for spoken commands, it means the user has finished speaking. This is the last of the three <code>select*</code> events to be sent.<br />
Also available through the <a href="xrsession/onselectend"><code>onselectend</code></a> event handler property.</td></tr><tr class="odd"><td><a href="xrsession/selectstart_event"><code>selectstart</code></a></td><td>An event of type <code>XRInputSourceEvent</code> which is sent to the session object when one of its input devices is first engaged by the user in such a way as to cause the primary action to begin. This is the first of the <code>session*</code> event to be sent.<br />
Also available through the <a href="xrsession/onselectstart"><code>onselectstart</code></a> event handler property.</td></tr><tr class="even"><td><a href="xrsession/squeeze_event"><code>squeeze</code></a></td><td>An <a href="xrinputsourceevent"><code>XRInputSourceEvent</code></a> sent to indicate that a <a href="webxr_device_api/inputs#primary_squeeze_actions">primary squeeze action</a> has successfully completed. This indicates that the device being squeezed has been released, and may represent dropping a grabbed object, for example. It is sent immediately before the <code>squeezeend</code> event is sent to indicate that the squeeze action is over.<br />
Also available through the <a href="xrsession/onsqueeze"><code>onsqueeze</code></a> event handler property.</td></tr><tr class="odd"><td><a href="xrsession/squeezeend_event"><code>squeezeend</code></a></td><td>An <a href="xrinputsourceevent"><code>XRInputSourceEvent</code></a> sent to the <code>XRSession</code> when the <a href="webxr_device_api/inputs#primary_squeeze_actions">primary squeeze action</a> ends, whether or not the action was successful.<br />
Also available using the <a href="xrsession/onsqueezeend"><code>onsqueezeend</code></a> event handler property.</td></tr><tr class="even"><td><a href="xrsession/squeezestart_event"><code>squeezestart</code></a></td><td>An event of type <a href="xrinputsourceevent"><code>XRInputSourceEvent</code></a> which is sent to the <code>XRSession</code> when the user initially squeezes a squeezable controller. This may be, for example, a trigger which is used to represent grabbing objects, or might represent actual squeezing when wearing a haptic glove.<br />
Also available through the <a href="xrsession/onsqueezestart"><code>onsqueezestart</code></a> event handler property.</td></tr><tr class="odd"><td><a href="xrsession/visibilitychange_event"><code>visibilitychange</code></a></td><td>An <a href="xrsessionevent"><code>XRSessionEvent</code></a> which is sent to the session when its visibility state as indicated by the <a href="xrsession/visibilitystate"><code>visibilityState</code></a> changes.<br />
Also available through the <a href="xrsession/onvisibilitychange"><code>onvisibilitychange</code></a> event handler property.</td></tr></tbody></table>

Example
-------

This example establishes a new `XRSession` in `inline` mode so that it can be displayed within an HTML element, avoiding the need for a dedicated AR or VR viewing device such as a headset.

    const XR = navigator.xr;

    if (XR) {
      XR.requestSession("inline").then((xrSession) => {
        xrSession.requestReferenceSpace("local").then((xrReferenceSpace) => {
          xrSession.requestAnimationFrame((time, xrFrame) => {
            let viewer = xrFrame.getViewerPose(xrReferenceSpace);

            gl.bindFramebuffer(xrWebGLLayer.framebuffer);

            for (xrView of viewer.views) {
              let xrViewport = xrWebGLLayer.getViewport(xrView);
              gl.viewport(xrViewport.x, xrViewport.y,
                          xrViewport.width, xrViewport.height);
            }
          });
        });
      });
    } else {
      /* WebXR is not available */
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrsession-interface">WebXR Device API<br />
<span class="small">The definition of 'XRSession' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRSession`

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

`domOverlayState`

83

83

No

No

No

No

No

83

No

No

No

No

`end`

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

`end_event`

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

`environmentBlendMode`

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

`inputsourceschange_event`

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

`interactionMode`

84

84

No

No

No

No

No

84

No

No

No

No

`onend`

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

`onselect`

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

`onsqueeze`

83

83

No

No

No

No

No

83

No

No

No

13.0

`onsqueezeend`

83

83

No

No

No

No

No

83

No

No

No

13.0

`onsqueezestart`

83

83

No

No

No

No

No

83

No

No

No

13.0

`onvisibilitychange`

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

`renderState`

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

`requestAnimationFrame`

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

`requestHitTestSource`

81

81

No

No

No

No

No

81

No

No

No

12.1

`requestHitTestSourceForTransientInput`

81

81

No

No

No

No

No

81

No

No

No

13.0

`requestReferenceSpace`

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

`select_event`

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

`selectend_event`

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

`selectstart_event`

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

`updateRenderState`

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

`visibilitychange_event`

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

`visibilityState`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession</a>
