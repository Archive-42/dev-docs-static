XRSessionEvent()
================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The WebXR Device API's `XRSessionEvent()` constructor creates and returns a new [`XRSessionEvent`](../xrsessionevent) object. These objects represent events announcing state changes in an [`XRSession`](../xrsession) representing an augmented or virtual reality session.

Syntax
------

    newXRSessionEvent = new XRSessionEvent(type, eventInitDict);

### Parameters

`type`  
A [`DOMString`](../domstring) indicating which of the events represented by objects of type `XRSessionEvent` this particular object represents. See [Event types](#event%0A____types) for a list of the permitted values.

`eventInitDict`  
An object conforming to the [`XRSessionEventInit`](../xrsessioneventinit) dictionary which contains values to be applied to the newly-created event object. Permitted values are:

[`session`](../xrsessioneventinit/session)  
The [`XRSession`](../xrsession) to which the event is to be delivered.

### Return value

A newly-created [`XRSessionEvent`](../xrsessionevent) object representing an object of the specfied type and configured as described by the `eventInitDict` parameter.

Event types
-----------

*The following events are represented using the `XRSessionEvent` interface, and are permitted values for its `type` property.*

[`end`](../xrsession/end_event)  
Fired at the session when it has ended, after being terminated by the application or the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

[`visibilitychange`](../xrsession/visibilitychange_event)  
Fired at the session whenever its visibility state changes.

Examples
--------

This example creates a listiener that watches for the visibility state of the session to change. It reacts by calling a function `mySessionVisible()` with a Boolean indicating whether or not the session is visible; this function might, for instance, spin up or reconfigure a worker that handles rendering the scene.

    xrSession.addEventListener("visibilitystate", e => {
      switch(e.session.visibilitystate) {
        case "visible":
        case "visible-blurred":
          mySessionVisible(true);
          break;
        case "hidden":
          mySessionVisible(false);
          break;
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsessionevent-xrsessionevent">WebXR Device API<br />
<span class="small">The definition of 'XRSessionEvent() constructor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRSessionEvent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSessionEvent/XRSessionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSessionEvent/XRSessionEvent</a>
