SourceBuffer.abort()
====================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `abort()` method of the [`SourceBuffer`](../sourcebuffer) interface aborts the current segment and resets the segment parser.

Syntax
------

    sourceBuffer.abort();

### Parameters

None.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td>The <a href="../mediasource/readystate"><code>MediaSource.readyState</code></a> property of the parent media source is not equal to <code>open</code>, or this <code>SourceBuffer</code> has been removed from the <a href="../mediasource"><code>MediaSource</code></a>.</td></tr></tbody></table>

Example
-------

The spec description of `abort()` is somewhat confusing — consider for example step 1 of [reset parser state](https://w3c.github.io/media-source/index.html#sourcebuffer-reset-parser-state). The MSE API is fully asynchronous, but this step seems to suggest a synchronous (blocking) operation, which doesn't make sense.

Saying that, current implementations can be useful in certain situations, when you want to stop the current append (or whatever) operation occurring on a sourcebuffer, and then immediately start performing operations on it again. For example, consider this code:

    sourceBuffer.addEventListener('updateend', function (_) {
      ...
    });

    sourceBuffer.appendBuffer(buf);

Let's say that after the call to `appendBuffer` BUT before the `updateend` event fires (i.e. a buffer is being appended but the operation has not yet completed) a user "scrubs" the video seeking to a new point in time. In this case you would want to manually call `abort()` on the source buffer to stop the decoding of the current buffer, then fetch and append the newly requested segment that relates to the current new position of the video.

You can see something similar in action in Nick Desaulnier's [bufferWhenNeeded demo](https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferWhenNeeded.html) — in [line 48, an event listener is added to the playing video](https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferWhenNeeded.html#L48) so a function called `seek()` is run when the `seeking` event fires. In [lines 92-101, the seek() function is defined](https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferWhenNeeded.html#L92-L101) — note that `abort()` is called if [`MediaSource.readyState`](../mediasource/readystate) is set to `open`, which means that it is ready to receive new source buffers — at this point it is worth aborting the current segment and just getting the one for the new seek position (see `checkBuffer()` and `getCurrentSegment()`.)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#dom-sourcebuffer-abort">Media Source Extensions<br />
<span class="small">The definition of 'abort()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`abort`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

No

14

No

2.0

See also
--------

-   [`MediaSource`](../mediasource)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/abort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/abort</a>
