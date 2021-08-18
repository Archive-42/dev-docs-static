WritableStreamDefaultController
===============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `WritableStreamDefaultController` interface of the [Streams API](streams_api) represents a controller allowing control of a [`WritableStream`](writablestream)'s state. When constructing a `WritableStream`, the underlying sink is given a corresponding `WritableStreamDefaultController` instance to manipulate.

Constructor
-----------

None. `WritableStreamDefaultController` instances are created automatically during `WritableStream` construction.

Properties
----------

None.

Methods
-------

[`WritableStreamDefaultController.error()`](writablestreamdefaultcontroller/error)  
Causes any future interactions with the associated stream to error.

Examples
--------

    const writableStream = new WritableStream({
      start(controller) {
        // do stuff with controller

        // error stream if necessary
        controller.error('My stream is broken');
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#ws-default-controller-class">Streams<br />
<span class="small">The definition of 'WritableStreamDefaultController' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WritableStreamDefaultController`

58

≤18

No

No

45

14.1

58

58

No

43

14.5

7.0

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultController" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultController</a>
