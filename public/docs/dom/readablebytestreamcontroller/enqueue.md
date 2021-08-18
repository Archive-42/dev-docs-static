# ReadableByteStreamController.enqueue()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `enqueue()` method of the [`ReadableByteStreamController`](../readablebytestreamcontroller) interface enqueues a given chunk in the associated stream.

## Syntax

    readableByteStreamController.enqueue(chunk);

### Parameters

_chunk_  
The chunk to enqueue.

### Return value

`undefined`.

### Exceptions

TypeError  
The source object is not a `ReadableByteStreamController`, or the stream cannot be read for some other reason, or the chunk is not an object, or the chunk's internal array buffer is non-existent or detached.

## Examples

TBD.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rbs-controller-enqueue">Streams<br />
<span class="small">The definition of 'enqueue()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`enqueue`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableByteStreamController/enqueue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableByteStreamController/enqueue</a>
