# NDEFReader

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `NDEFReader` interface of the [Web NFC API](web_nfc_api) is an abstract interface used to read from and write data to compatible NFC devices, e.g. NFC tags supporting NDEF, when these devices are within the reader's magnetic induction field.

## Constructor

[`NDEFReader.NDEFReader()`](ndefreader/ndefreader) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns an `NDEFReader` with configuration specified in the parameters or default ones if no parameters are specified.

## Properties

_In addition to the properties listed below, `NDEFReader` inherits properties from its parent interface, [`EventTarget`](eventtarget)._

[`NDEFReader.onreading`](ndefreader/onreading) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
An event handler for `reading` event, that notifies about availability of a new reading.

[`NDEFReader.onreadingerror`](ndefreader/onreadingerror) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
An event handler for the `readingerror` event, which is fired when an error occurs during reading.

## Methods

_The `NDEFReader` interface inherits the methods of [`EventTarget`](eventtarget), its parent interface._

[`NDEFReader.scan()`](ndefreader/scan) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Called to activate the reader (after ensuring hardware and UA compatibility and obtaining permission from the user) or get an error explaining why feature is not available.

[`NDEFReader.write()`](ndefreader/write) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Called to write NDEF message to a tag (after ensuring hardware and UA compatibility and obtaining permission from the user) or get an error explaining why feature is not available.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/#dom-ndefreader">Web NFC, NDEFReader</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

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

`NDEFReader`

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

`NDEFReader`

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

`onreading`

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

`onreadingerror`

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

`scan`

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

`write`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NDEFReader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NDEFReader</a>
