PromiseRejectionEvent.reason
============================

The [`PromiseRejectionEvent`](../promiserejectionevent) `reason` read-only property is any JavaScript value or [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) which provides the reason passed into [`Promise.reject()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/reject). This in theory provides information about why the promise was rejected.

Syntax
------

    reason = PromiseRejectionEvent.reason

### Value

A value or object which provides information you can use to understand why the promise was rejected. This could be anything from an error code to an object with text, links, and whatever else you might wish to include.

Examples
--------

    window.onunhandledrejection = function(e) {
      console.log(e.reason);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-promiserejectionevent-reason">HTML Living Standard<br />
<span class="small">The definition of 'PromiseRejectionEvent.reason' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`reason`

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

-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [`PromiseRejectionEvent`](../promiserejectionevent)
-   `rejectionhandled`
-   `unhandledrejection`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent/reason" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent/reason</a>
