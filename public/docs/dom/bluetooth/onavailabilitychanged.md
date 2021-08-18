# Bluetooth.onavailabilitychanged

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onavailabilitychanged` property of the [`Bluetooth`](../bluetooth) interface is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `availabilitychanged` events that fire when the Bluetooth system as a whole becomes available or unavailable to the [User Agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

## Syntax

    Bluetooth.onavailabilitychanged = functionRef;

### Value

`functionRef` is the handler function to be called when the Bluetooth `availabilitychanged` event fires.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#bluetooth">Web Bluetooth<br />
<span class="small">The definition of 'Bluetooth' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onavailabilitychanged`

56

macOS only.

56

Linux and versions of Windows earlier than 10.

70

Windows 10.

79

macOS only.

79

Linux and versions of Windows earlier than 10.

79

Windows 10.

No

No

43

macOS only.

43

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

56

No

43

No

6.0

## See also

- [`Bluetooth.getAvailability`](getavailability)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Bluetooth/onavailabilitychanged" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Bluetooth/onavailabilitychanged</a>
