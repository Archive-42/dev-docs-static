# ReadableStreamDefaultController.error()

The `error()` method of the [`ReadableStreamDefaultController`](../readablestreamdefaultcontroller) interface causes any future interactions with the associated stream to error.

**Note**: The `error()` method can be called more than once, and can be called when the stream is not readable.

## Syntax

    readableStreamDefaultController.error(e);

### Parameters

_e_  
The error you want future interactions to fail with.

### Return value

`undefined`.

### Exceptions

TypeError  
The source object is not a `ReadableStreamDefaultController`, or the stream is not readable for some other reason.

## Examples

The [A readable stream with an underlying push source and backpressure support](https://streams.spec.whatwg.org/#example-rs-push-backpressure) example in the spec provides a good example of using [`ReadablestreamDefaultController.desiredSize`](desiredsize) to manually detect when the stream is full and apply backpressure, and also of using `error()` to manually trigger a stream error if another part of the system it relies on fails.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rs-default-controller-error">Streams<br />
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

?

?

65

No

?

No

?

?

65

?

No

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultController/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultController/error</a>
