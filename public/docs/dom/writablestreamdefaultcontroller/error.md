WritableStreamDefaultController.error()
=======================================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `error()` method of the [`WritableStreamDefaultController`](../writablestreamdefaultcontroller) interface causes any future interactions with the associated stream to error.

This method is rarely used, since usually it suffices to return a rejected promise from one of the underlying sink’s methods. However, it can be useful for suddenly shutting down a stream in response to an event outside the normal lifecycle of interactions with the underlying sink.

Syntax
------

    writableStreamDefaultController.error(e);

### Parameters

e  
A [`DOMString`](../domstring) representing the error you want future interactions to fail with.

### Return value

`undefined`.

### Exceptions

TypeError  
The stream you are trying to error is not a [`WritableStream`](../writablestream).

Examples
--------

    const writableStream = new WritableStream({
      start(controller) {
        // do stuff with controller

        // error stream if necessary
        controller.error('My error is broken');
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
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#ws-default-controller-error">Streams<br />
<span class="small">The definition of 'error()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`error`

?

16

No

No

?

14.1

?

?

No

?

14.5

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultController/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultController/error</a>
