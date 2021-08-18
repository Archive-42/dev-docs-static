# ReadableByteStreamController.error()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `error()` method of the [`ReadableByteStreamController`](../readablebytestreamcontroller) interface causes any future interactions with the associated stream to error.

## Syntax

    readableByteStreamController.error(e);

### Parameters

_e_  
The error you want future interactions to fail with.

### Return value

`undefined`.

### Exceptions

TypeError  
The source object is not a `ReadableByteStreamController`, or the stream is not readable for some other reason.

## Examples

TBD.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rbs-controller-error">Streams<br />
<span class="small">The definition of 'error()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`error`

89

89

No

No

75

No

89

89

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableByteStreamController/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableByteStreamController/error</a>
