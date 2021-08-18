# ReadableStreamBYOBReader.ReadableStreamBYOBReader()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ReadableStreamBYOBReader()` constructor creates and returns a `ReadableStreamBYOBReader` object instance.

**Note**: You generally wouldn't use this constructor manually; instead, you'd use the [`ReadableStream.getReader()`](../readablestream/getreader) method.

## Syntax

    var readableStreamBYOBReader = new ReadableStreamBYOBReader(stream);

### Parameters

stream  
The [`ReadableStream`](../readablestream) to be read.

### Return value

An instance of the [`ReadableStreamBYOBReader`](../readablestreambyobreader) object.

### Exceptions

TypeError  
The supplied `stream` parameter is not a [`ReadableStream`](../readablestream), or it is already locked for reading by another reader, or its stream controller is not a [`ReadableByteStreamController`](../readablebytestreamcontroller).

## Examples

TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#byob-reader-constructor">Streams<br />
<span class="small">The definition of 'ReadableStreamBYOBReader()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ReadableStreamBYOBReader`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader/ReadableStreamBYOBReader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader/ReadableStreamBYOBReader</a>
