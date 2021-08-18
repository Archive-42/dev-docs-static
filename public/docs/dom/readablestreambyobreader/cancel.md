# ReadableStreamBYOBReader.cancel()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `cancel()` method of the [`ReadableStreamBYOBReader`](../readablestreambyobreader) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the stream is canceled. Calling this method signals a loss of interest in the stream by a consumer.

**Note**: If the reader is active, the `cancel()` method behaves the same as that for the associated stream ([`ReadableStream.cancel()`](../readablestream/cancel)).

## Syntax

    var promise = readableStreamBYOBReader.cancel(reason);

### Parameters

reason <span class="badge inline optional">Optional</span>  
A human-readable reason for the cancellation. The underlying source may or may not use it.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), which fulfills with the value given in the `reason` parameter.

### Exceptions

TypeError  
The source object is not a `ReadableStreamBYOBReader`, or the stream has no owner.

## Examples

TBD.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#byob-reader-cancel">Streams<br />
<span class="small">The definition of 'cancel()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`cancel`

No

No

No

No

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader/cancel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader/cancel</a>
