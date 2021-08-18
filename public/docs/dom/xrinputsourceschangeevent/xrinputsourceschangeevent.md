XRInputSourcesChangeEvent()
===========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `XRInputSourcesChangeEvent()` constructor creates and returns a new [`XRInputSourcesChangeEvent`](../xrinputsourceschangeevent) object, representing an update to the list of available [WebXR](../webxr_device_api) input devices. You won't typically call this constructor yourself, as these events are created and sent to you by the WebXR system.

Syntax
------

    newInputSourcesChangeEvent = new XRInputSourcesChangeEvent(type, eventInitDict);

### Parameters

`type`  
A [`DOMString`](../domstring) indicating the type of event which has occurred. This string must always be `inputsourceschange`.

`eventInitDict`  
An object conforming to the [`XRInputSourcesChangeEventInit`](../xrinputsourceschangeeventinit) dictionary, prodividing the initial values for the event.

### Return value

A newly-created [`XRInputSourcesChangeEvent`](../xrinputsourceschangeevent) object configured based upon the input parameters provided.

Event types
-----------

[`inputsourceschange`](../xrsession/inputsourceschange_event)  
Delivered to the [`XRSession`](../xrsession) when the set of input devices available to it changes.

Example
-------

The following snippet of code creates a new `XRInputSourcesChangeEvent` object indicating that a single new input source, described by an [`XRInputSource`](../xrinputsource) object named `newInputSource`, has been added to the system.

    let iscEvent = new XRInputSourcesChangeEvent("inputsourceschange", { session: xrSession,
                               added: [newInputSource], removed: [] });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsourceschangeevent-xrinputsourceschangeevent">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourcesChangeEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRInputSourcesChangeEvent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourcesChangeEvent/XRInputSourcesChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourcesChangeEvent/XRInputSourcesChangeEvent</a>
