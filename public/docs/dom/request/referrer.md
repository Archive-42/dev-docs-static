Request.referrer
================

The `referrer` read-only property of the [`Request`](../request) interface is set by the user agent to be the referrer of the Request. (e.g., `client`, `no-referrer`, or a URL.)

**Note**: If `referrer`'s value is `no-referrer`, it returns an empty string.

Syntax
------

    var myReferrer = request.referrer;

### Value

A [`DOMString`](../domstring) representing the request's referrer.

Example
-------

In the following snippet, we create a new request using the [`Request.Request()`](request) constructor (for an image file in the same directory as the script), then save the request referrer in a variable:

    var myRequest = new Request('flowers.jpg');
    var myReferrer = myRequest.referrer; // returns "about:client" by default

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-referrer">Fetch<br />
<span class="small">The definition of 'referrer' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`referrer`

42

41

14

47

No

29

28

10.1

42

42

No

29

28

10.3

4.0

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/referrer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/referrer</a>
