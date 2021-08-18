# ReadableStreamBYOBReader.releaseLock()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `releaseLock()` method of the [`ReadableStreamBYOBReader`](../readablestreambyobreader) interface releases the reader's lock on the stream. After the lock is released, the reader is no longer active.

If the associated stream is errored when the lock is released, the reader will appear errored in that same way subsequently; otherwise, the reader will appear closed.

A reader’s lock cannot be released while it still has a pending read request, i.e., if a promise returned by the reader’s [`ReadableStreamBYOBReader.read()`](read) method has not finished. This will result in a `TypeError` being thrown.

## Syntax

    readableStreamBYOBReader.releaseLock();

### Parameters

None.

### Return value

`undefined`.

### Exceptions

TypeError  
The source object is not a `ReadableStreamBYOBReader`, or a read request is pending.

## Examples

TBD.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#byob-reader-release-lock">Streams<br />
<span class="small">The definition of 'releaseLock()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`releaseLock`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader/releaseLock" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader/releaseLock</a>
