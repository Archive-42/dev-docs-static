WritableStreamDefaultWriter.desiredSize
=======================================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `desiredSize` read-only property of the [`WritableStreamDefaultWriter`](../writablestreamdefaultwriter) interface returns the desired size required to fill the stream's internal queue.

Syntax
------

    var desiredSize = writableStreamDefaultWriter.desiredSize;

### Value

An integer. Note that this can be negative if the queue is over-full.

The value will be `null` if the stream cannot be successfully written to (due to either being errored, or having an abort queued up), and zero if the stream is closed.

### Exceptions

TypeError  
The writer’s lock is released.

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

    ...

    // return stream's desired size
    let size = writer.desiredSize;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#default-writer-desired-size">Streams<br />
<span class="small">The definition of 'desiredSize' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`desiredSize`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter/desiredSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter/desiredSize</a>
