ReadableStream.locked
=====================

The `locked` read-only property of the [`ReadableStream`](../readablestream) interface returns whether or not the readable stream is <a href="https://streams.spec.whatwg.org/#lock" id="ref-for-locked-to-a-reader②">locked to a reader</a>.

Syntax
------

    var locked = readableStream.locked;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the readable stream is locked.

Examples
--------

    const stream = new ReadableStream({
      ...
    });

    const reader = stream.getReader();

    stream.locked
    // should return true, as the stream has been locked to a reader

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rs-locked">Streams<br />
<span class="small">The definition of 'locked' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`locked`

43

14

65

No

30

10.1

43

43

65

30

10.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream/locked" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream/locked</a>
