# NDEFReadingEvent

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `NDEFReadingEvent` interface represents events dispatched on new NFC readings obtained by [`NDEFReader`](ndefreader).

## Constructor

<span class="page-not-created">`NDEFReadingEvent.NDEFReadingEvent()`</span>  
Creates an `NDEFReadingEvent` event with the given parameters.

## Properties

_Also inherits properties from its parent [`Event`](event)_.

<span class="page-not-created">`NDEFReadingEvent.serialNumber`</span> <span class="badge inline readonly">Read only </span>  
Represents the serial number of the device used for anti-collision and identification, or empty string in case none is available.

<span class="page-not-created">`NDEFReadingEvent.message`</span> <span class="badge inline readonly">Read only </span>  
Represents the received message as an [`NDEFMessage`](ndefmessage) object.

## Methods

_Inherits methods from its parent [`Event`](event)_.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/#dom-ndefreadingevent">Web NFC, NDEFReadingEvent</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

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

`NDEFReadingEvent`

No

No

No

No

No

No

No

89

No

No

No

No

`NDEFReadingEvent`

No

No

No

No

No

No

No

89

No

No

No

No

`message`

No

No

No

No

No

No

No

89

No

No

No

No

`secure_context_required`

No

No

No

No

No

No

No

89

No

No

No

No

`serialNumber`

No

No

No

No

No

No

No

89

No

No

No

No

## See also

- [`NDEFReader`](ndefreader), interface that this event is fired on.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NDEFReadingEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NDEFReadingEvent</a>
