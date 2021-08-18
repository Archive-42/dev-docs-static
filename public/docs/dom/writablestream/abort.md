WritableStream.abort()
======================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `abort()` method of the [`WritableStream`](../writablestream) interface aborts the stream, signaling that the producer can no longer successfully write to the stream and it is to be immediately moved to an error state, with any queued writes discarded.

Syntax
------

    var promise = writableStream.abort(reason);

### Parameters

reason  
A [`DOMString`](../domstring) providing a human-readable reason for the abort.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), which fulfills with the value given in the `reason` parameter.

### Exceptions

TypeError  
The stream you are trying to abort is not a [`WritableStream`](../writablestream), or it is locked.

Examples
--------

    const writableStream = new WritableStream({
      write(chunk) {
        ...
      },
      close() {
        ...
      },
      abort(err) {
        ...
      }
    }, queuingStrategy);

    ...

    // abort the stream later on, when required
    writableStream.abort();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#ws-abort">Streams<br />
<span class="small">The definition of 'abort()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

59

16

No

No

47

14.1

59

59

No

44

14.5

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStream/abort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStream/abort</a>
