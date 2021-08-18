XRInputSourcesChangeEvent
=========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The WebXR Device API interface `XRInputSourcesChangeEvent` is used to represent the [`inputsourceschange`](xrsession/inputsourceschange_event) event sent to an [`XRSession`](xrsession) when the set of available WebXR input controllers changes.

Constructor
-----------

[`XRInputSourcesChangeEvent()`](xrinputsourceschangeevent/xrinputsourceschangeevent)  
Creates and returns a new `XRInputSourcesChangeEvent` object configured as indicated by the given [`XRInputSourcesChangeEventInit`](xrinputsourceschangeeventinit) object. The specified type must be `inputsourceschange`, which is the only event that uses this interface.

Properties
----------

 [`added`](xrinputsourceschangeevent/added) <span class="badge inline readonly">Read only </span>   
An array of zero or more [`XRInputSource`](xrinputsource) objects, each representing an input device which has been newly connected or enabled for use.

 [`removed`](xrinputsourceschangeevent/removed) <span class="badge inline readonly">Read only </span>   
An array of zero or more [`XRInputSource`](xrinputsource) objects representing the input devices newly connected or enabled for use.

 [`session`](xrinputsourceschangeevent/session) <span class="badge inline readonly">Read only </span>   
The [`XRSession`](xrsession) to which this input source change event is being directed.

Methods
-------

*While `XRInputSourcesChangeEvent` defines no methods of its own, it inherits methods from its parent interface, [`Event`](event).*

Event types
-----------

[`inputsourceschange`](xrsession/inputsourceschange_event)  
Delivered to the [`XRSession`](xrsession) when the set of input devices available to it changes.

Examples
--------

The following example shows how to set up an event handler which uses `inputsourceschange` events to detect newly-available pointing devices and to load their models in preparation to display them in the next animation frame.

    xrSession.addEventListener("inputsourceschange", onInputSourcesChange);

    function onInputSourcesChange(event) {
      for (let input of event.added) {
        if (input.targetRayMode == "tracked-pointer") {
          loadControllerMesh(input);
        }
      }
    }

You can also add a handler for `inputsourceschange` events by setting the [`oninputsourceschange`](xrsession/oninputsourceschange) event handler:

    xrSession.oninputsourceschange = onInputSourcesChange;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrinputsourceschangeevent">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourcesChangeEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`added`

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

`removed`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourcesChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourcesChangeEvent</a>
