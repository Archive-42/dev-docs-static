XRSessionEvent
==============

The [WebXR Device API](webxr_device_api)'s `XRSessionEvent` interface describes an event which indicates the change of the state of an [`XRSession`](xrsession). These events occur, for example, when the session ends or the visibility of its context changes.

Constructor
-----------

[`XRSessionEvent()`](xrsessionevent/xrsessionevent)  
Creates and returns a new `XRSessionEvent` object configured using the specified [`XRSessionEventInit`](xrsessioneventinit) object's values as available.

Properties
----------

*In addition to properties inherited from its parent interface, [`Event`](event), `XRSessionEvent` provides the following:*

 [`session`](xrsessionevent/session) <span class="badge inline readonly">Read only </span>   
The [`XRSession`](xrsession) to which the event refers.

Methods
-------

*While `XRSessionEvent` defines no methods, it inherits methods from its parent interface, [`Event`](event).*

Session event types
-------------------

*The following events are represented using the `XRSessionEvent` interface, and are permitted values for its `type` property.*

[`end`](xrsession/end_event)  
Fired at the session when it has ended, after being terminated by the application or the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

[`visibilitychange`](xrsession/visibilitychange_event)  
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrsessionevent">WebXR Device API<br />
<span class="small">The definition of 'XRSessionEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`session`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSessionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSessionEvent</a>
