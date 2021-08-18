WritableStreamDefaultWriter.releaseLock()
=========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `releaseLock()` method of the [`WritableStreamDefaultWriter`](../writablestreamdefaultwriter) interface releases the writer's lock on the corresponding stream. After the lock is released, the writer is no longer active. If the associated stream is errored when the lock is released, the writer will appear errored in the same way from now on; otherwise, the writer will appear closed.

Syntax
------

    writableStreamDefaultWritere.releaseLock()

### Parameters

None.

### Return value

`undefined`.

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

    // release writer's lock on the stream when desired
    writer.releaseLock();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#default-reader-release-lock">Streams<br />
<span class="small">The definition of 'releaseLock()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`releaseLock`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter/releaseLock" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter/releaseLock</a>
