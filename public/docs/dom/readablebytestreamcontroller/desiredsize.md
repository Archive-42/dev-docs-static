# ReadableByteStreamController.desiredSize

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `desiredSize` read-only property of the [`ReadableByteStreamController`](../readablebytestreamcontroller) interface returns the desired size required to fill the stream's internal queue.

## Syntax

    var desiredSize = readableByteStreamController.desiredSize;

### Value

An integer. Note that this can be negative if the queue is over-full.

## Examples

TBD.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rbs-controller-desired-size">Streams<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableByteStreamController/desiredSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableByteStreamController/desiredSize</a>
