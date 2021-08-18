SourceBuffer.appendStream()
===========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `appendStream()` method of the [`SourceBuffer`](../sourcebuffer) interface appends media segment data from a `ReadableStream` object to the `SourceBuffer`.

Syntax
------

    sourceBuffer.appendStream(stream, maxSize);

### Parameters

stream  
The [`ReadableStream`](../readablestream) that is the source of the media segment data you want to append to the `SourceBuffer`.

maxSize  
An unsigned long value indicating the maximum number of bytes that can be appended in this operation.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

None.

Example
-------

TBD.

Browser compatibility
---------------------

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

`appendStream`

No

12-79

No

?

No

?

?

?

No

?

No

?

See also
--------

-   [`MediaSource`](../mediasource)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/appendStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/appendStream</a>
