# ReadableStreamDefaultController.desiredSize

The `desiredSize` read-only property of the [`ReadableStreamDefaultController`](../readablestreamdefaultcontroller) interface returns the desired size required to fill the stream's internal queue.

## Syntax

    var desiredSize = readableStreamDefaultController.desiredSize;

### Value

An integer. Note that this can be negative if the queue is over-full.

## Examples

The [A readable stream with an underlying push source and backpressure support](https://streams.spec.whatwg.org/#example-rs-push-backpressure) example in the spec provides a good example of using `desiredSize` to manually detect when the stream is full and apply backpressure, and also of using [`ReadablestreamDefaultController.error()`](error) to manually trigger a stream error if another part of the system it relies on fails.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rs-default-controller-desired-size">Streams<br />
<span class="small">The definition of 'desiredSize' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`desiredSize`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultController/desiredSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultController/desiredSize</a>
