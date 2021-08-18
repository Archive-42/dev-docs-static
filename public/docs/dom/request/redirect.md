Request.redirect
================

The `redirect` read-only property of the [`Request`](../request) interface contains the mode for how redirects are handled.

Syntax
------

    var myRedirect = request.redirect;

### Value

A `RequestRedirect` enum value, which can be one the following strings:

-   `follow`
-   `error`
-   `manual`

If not specified when the request is created, it takes the default value of `follow`.

Example
-------

In the following snippet, we create a new request using the [`Request.Request()`](request) constructor (for an image file in the same directory as the script), then save the request `redirect` value in a variable:

    var myRequest = new Request('flowers.jpg');
    var myCred = myRequest.redirect;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-redirect">Fetch<br />
<span class="small">The definition of 'redirect' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`redirect`

46

14

43

No

Yes

10.1

No

46

43

Yes

10.3

5.0

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/redirect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/redirect</a>
