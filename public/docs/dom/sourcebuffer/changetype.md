SourceBuffer.changeType()
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `changeType()` method of the [`SourceBuffer`](../sourcebuffer) interface sets the MIME type that future calls to [`appendBuffer()`](appendbuffer) should expect the new media data to conform to. This makes it possible to change codecs or container type mid-stream.

One scenario in which this is helpful is to support adapting the media source to changing bandwidth availability, by transitioning from one codec to another as resource constraints change.

Syntax
------

    sourceBuffer.changeType(type);

### Parameters

`type`  
A [`DOMString`](../domstring) specifying the MIME type that future buffers will conform to.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

`TypeError`  
The specified string is empty, rather than indicating a valid MIME type.

`InvalidStateError`  
The [`SourceBuffer`](../sourcebuffer) is not a member of the parent media source's [`sourceBuffers`](../mediasource/sourcebuffers) list, or the buffer's [`updating`](updating) property indicates that a previously queued [`appendBuffer()`](appendbuffer) or [`remove()`](remove) is still being processed.

`NotSupportedError`  
The specified MIME type is not supported, or is not supported with the types of [`SourceBuffer`](../sourcebuffer) objects present in the [`MediaSource.sourceBuffers`](../mediasource/sourcebuffers) list.

Usage notes
-----------

If the parent [`MediaSource`](../mediasource) is in its `"ended"` [`readyState`](../mediasource/readystate), calling `changeType()` will transition the media source to the `"open"` `readyState` and fire a simple event named `sourceopen` at the parent media source.

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

`changeType`

70

79

63

?

?

?

70

70

No

?

No

10.0

See also
--------

-   [`MediaSource`](../mediasource)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/changeType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/changeType</a>
