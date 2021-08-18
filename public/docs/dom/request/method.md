Request.method
==============

The `method` read-only property of the [`Request`](../request) interface contains the request's method (`GET`, `POST`, etc.)

Syntax
------

    var myMethod = request.method;

### Value

A [`ByteString`](../bytestring) indicating the method of the request.

Example
-------

In the following snippet, we create a new request using the [`Request.Request()`](request) constructor (for an image file in the same directory as the script), then save the method of the request in a variable:

    var myRequest = new Request('flowers.jpg');
    var myMethod = myRequest.method; // GET

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-method">Fetch<br />
<span class="small">The definition of 'method' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`method`

42

41

14

39

34

No

29

28

10.1

42

42

39

29

28

10.3

4.0

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/method" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/method</a>
