ReadableStreamBYOBReader.closed
===============================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `closed` read-only property of the [`ReadableStreamBYOBReader`](../readablestreambyobreader) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills when the stream closes or the reader's lock is released, or rejects if the stream throws an error. This property enables you to write code that responds to an end to the streaming process.

Syntax
------

    var closed = readableStreamBYOBReader.closed;

### Value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

Examples
--------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#byob-reader-closed">Streams<br />
<span class="small">The definition of 'closed' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`closed`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader/closed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader/closed</a>
