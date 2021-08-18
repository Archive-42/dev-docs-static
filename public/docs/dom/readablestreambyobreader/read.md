ReadableStreamBYOBReader.read()
===============================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `read()` method of the [`ReadableStreamBYOBReader`](../readablestreambyobreader) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an obect representing the next chunk in the stream's queue.

Syntax
------

    var promise = readableStreamBYOBReader.read(view);

### Parameters

view  
The view to be read into.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), which fulfills/rejects with a result depending on the state of the stream. The following are possible:

-   If a chunk is available, the promise fulfills with an object of the form `{ value: theChunk, done: false }`.
-   If the stream is closed, the promise fulfills with an object of the form `{ value: undefined, done: true }`.
-   If the stream throws an error, the promise rejects with the relevant error.

### Exceptions

TypeError  
The source object is not a `ReadableStreamBYOBReader`, the stream has no owner, the view is not an object or has become detached, or the view's length is 0.

Examples
--------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#byob-reader-read">Streams<br />
<span class="small">The definition of 'read()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`read`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader/read" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader/read</a>
