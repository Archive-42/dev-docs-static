Window: rejectionhandled event
==============================

The `rejectionhandled` event is sent to the script's global scope (usually [`window`](../window) but also [`Worker`](../worker)) whenever a JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is rejected but after the promise rejection has been handled. This can be used in debugging and for general application resiliency, in tandem with the [`unhandledrejection`](unhandledrejection_event) event, which is sent when a promise is rejected but there is no handler for the rejection.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../promiserejectionevent"><code>PromiseRejectionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../windoweventhandlers/onrejectionhandled"><code>onrejectionhandled</code></a></td></tr></tbody></table>

Example
-------

You can use the `rejectionhandled` event to log promises that get rejected to the console, along with the reasons why they were rejected:

    window.addEventListener("rejectionhandled", event => {
      console.log("Promise rejected; reason: " + event.reason);
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#unhandled-promise-rejections">HTML Living Standard<br />
<span class="small">The definition of 'rejectionhandled' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`rejectionhandled_event`

49

≤79

69

68

No

36

11

49

49

68

36

11.3

5.0

See also
--------

-   [Promise rejection events](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises#promise_rejection_events) in [Using Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
-   [`PromiseRejectionEvent`](../promiserejectionevent)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [`unhandledrejection`](unhandledrejection_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/rejectionhandled_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/rejectionhandled_event</a>
