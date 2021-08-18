WritableStreamDefaultWriter.closed
==================================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `closed` read-only property of the [`WritableStreamDefaultWriter`](../writablestreamdefaultwriter) interface returns a promise that fulfills if the stream becomes closed or the writer's lock is released, or rejects if the stream errors.

Syntax
------

    var closed = writableStreamDefaultWriter.closed;

### Value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

Examples
--------

    const writableStream = new WritableStream({
      start(controller) {
      },
      write(chunk, controller) {
        ...
      },
      close(controller) {
        ...
      },
      abort(err) {
        ...
      }
    }, queuingStrategy);

    ...

    const writer = writableStream.getWriter();

    ..

    // check if the stream is closed
    writer.closed.then(() => {
      console.log('writer closed');
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#default-writer-closed">Streams<br />
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

59

16

No

No

46

14.1

59

59

No

43

14.5

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter/closed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter/closed</a>
