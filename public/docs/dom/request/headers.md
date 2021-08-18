Request.headers
===============

The `headers` read-only property of the [`Request`](../request) interface contains the [`Headers`](../headers) object associated with the request.

Syntax
------

    var myHeaders = request.headers;

### Value

A [`Headers`](../headers) object.

Example
-------

In the following snippet, we create a new request using the [`Request.Request()`](request) constructor (for an image file in the same directory as the script), then save the request headers in a variable:

    var myRequest = new Request('flowers.jpg');
    var myHeaders = myRequest.headers; // Headers {}

To add a header to the [`Headers`](../headers) object we use [`Headers.append`](../headers/append); we then create a new `Request` along with a 2nd init parameter, passing headers in as an init option:

    var myHeaders = new Headers();
    myHeaders.append('Content-Type', 'image/jpeg');

    var myInit = {
      method: 'GET',
      headers: myHeaders,
      mode: 'cors',
      cache: 'default'
    };

    var myRequest = new Request('flowers.jpg', myInit);

    myContentType = myRequest.headers.get('Content-Type'); // returns 'image/jpeg'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-headers">Fetch<br />
<span class="small">The definition of 'headers' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`headers`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/headers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/headers</a>
