# InputDeviceCapabilities

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `InputDeviceCapabilities` interface of the [Input Device Capabilities API](inputdevicecapabilities_api) provides information about the physical device or a group of related devices responsible for generating input events. Events caused by the same physical input device get the same instance of this object, but the converse isn't true. For example, two mice with the same capabilities in a system may appear as a single `InputDeviceCapabilities` instance.

In some instances, `InputDeviceCapabilities` represents the capabilities of logical devices rather than physical devices. This allows, for example, touchscreen keyboards and physical keyboards to be represented the same way when they produce the same input.

## Constructors

[`InputDeviceCapabilities.InputDeviceCapabilities()`](inputdevicecapabilities/inputdevicecapabilities)  
Creates an `InputDeviceCapabilities` object.

## Properties

[`InputDeviceCapabilities.firesTouchEvents`](inputdevicecapabilities/firestouchevents)<span class="badge inline readonly">Read only </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the device dispatches touch events.

## Methods

None.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/InputDeviceCapabilities/#dom-uievent-sourcecapabilities">InputDeviceCapabilities<br />
<span class="small">The definition of 'sourceCapabilities' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`InputDeviceCapabilities`

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

`InputDeviceCapabilities`

47

≤79

?

No

?

No

47

47

?

?

No

5.0

`firesTouchEvents`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InputDeviceCapabilities" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InputDeviceCapabilities</a>
