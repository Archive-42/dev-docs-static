XRInputSourceEvent()
====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `XRInputSourceEvent()` constructor creates and returns a new [`XRInputSourceEvent`](../xrinputsourceevent) object describing an event (state change) which has occurred on a WebXR user input device represented by an [`XRInputSource`](../xrinputsource).

Syntax
------

    newInputSourceEvent = new XRInputSourceEvent(type, eventInitDict);

### Parameters

`type`  
A [`DOMString`](../domstring) indicating which of the input source events the new object will represent. Permitted values are listed under [Event types](#event_types) below.

`eventInitDict`  
An object based on the [`XRInputSourceEventInit`](../xrinputsourceeventinit) dictionary which contains the values to assign to the new event's properties.

### Return value

A new [`XRInputSourceEvent`](../xrinputsourceevent) object representing the event described by the given `type` and `eventInitDict`.

Event types
-----------

[`select`](../xrsession/select_event)  
Sent to an [`XRSession`](../xrsession) when the sending input source has fully completed a [primary action](../webxr_device_api/inputs#primary_actions).

[`selectend`](../xrsession/selectend_event)  
Sent to an [`XRSession`](../xrsession) when an ongoing [primary action](../webxr_device_api/inputs#primary_actions) ends, or when an input source with an ongoing primary action has been disconnected from the system.

[`selectstart`](../xrsession/selectstart_event)  
Sent to an [`XRSession`](../xrsession) when an input source begins its [primary action](../webxr_device_api/inputs#primary_actions), indicating that the user has begun a command-like input, such as pressing a trigger or button, issuing a spoken command, tapping on a touchpad, or the like.

[`squeeze`](../xrsession/squeeze_event)  
Sent to an [`XRSession`](../xrsession) when the sending input source has fully completed a [primary squeeze action](../webxr_device_api/inputs#primary_squeeze_actions).

[`squeezeend`](../xrsession/squeezeend_event)  
Sent to an [`XRSession`](../xrsession) when an ongoing [primary squeeze action](../webxr_device_api/inputs#primary_squeeze_actions) ends or when an input source with an ongoing primary squeeze action is disconnected.

[`squeezestart`](../xrsession/squeezestart_event)  
Sent to an [`XRSession`](../xrsession) when an input source begins its [primary squeeze action](../webxr_device_api/inputs#primary_squeeze_actions), indicating that the user has begun to grab, squeeze, or grip the controller.

Examples
--------

The code below sets up handlers for primary action events in order to determine when the user clicks on (shoots at/pokes at/whatever) objects in the scene.

    xrSession.addEventListener("select", event => {
      let targetRayPose = event.frame.getPose(event.inputSource.targetRaySpace, myRefSpace);

      if (targetRayPose) {
        let hit = myHitTest(targetRayPose.transform);
        if (hit) {
          /* handle the hit */
        }
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrinputsourceevent">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourceEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRInputSourceEvent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceEvent/XRInputSourceEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceEvent/XRInputSourceEvent</a>
