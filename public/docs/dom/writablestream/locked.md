WritableStream.locked
=====================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `locked` read-only property of the [`WritableStream`](../writablestream) interface returns a boolean indicating whether the `WritableStream` is locked to a writer.

Syntax
------

    var locked = writableStream.locked;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the writable stream is locked.

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

    const writer = writableStream.getWriter();

    writableStream.locked
    // should return true, as the stream has been locked to a writer

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#ws-locked">Streams<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStream/locked" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStream/locked</a>
