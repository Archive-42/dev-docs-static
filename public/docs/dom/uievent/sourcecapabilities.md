UIEvent.sourceCapabilities
==========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `UIEvent.sourceCapabilities` read-only property returns an instance of the [`InputDeviceCapabilities`](../inputdevicecapabilities) interface which provides information about the physical device responsible for generating a touch event. If no input device was responsible for the event, it returns `null`.

When a single user interaction with an input device generates a series of different input events, the `sourceCapabilities` property for all of them will point to the same instance of `InputDeviceCapabilities`. For example, when a user lifts their finger off of a touchscreen, several UIEvents may be generated including `touchend`, `mousedown`, `click`, and `focus`. All of these events must have the same `sourceCapabilities` representing the touchscreen.

A device is considered "responsible" for an event only when that interaction is part of the abstraction provided by the web platform. For example, many user agents allow a window to be resized with a mouse or a keyboard, but this detail is not exposed to the web platform in any way, and so the sourceCapabilities of a resize event will typically be null.

Syntax
------

    var iDC = event.sourceCapabilities

### Value

An instance of [`InputDeviceCapabilities`](../inputdevicecapabilities).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/InputDeviceCapabilities/#dom-uievent-sourcecapabilities">InputDeviceCapabilities<br />
<span class="small">The definition of 'sourceCapabilities' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`sourceCapabilities`

47

≤79

?

No

Yes

No

47

47

?

Yes

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/sourceCapabilities" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/sourceCapabilities</a>
