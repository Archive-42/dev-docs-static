Request.credentials
===================

The `credentials` read-only property of the [`Request`](../request) interface indicates whether the user agent should send cookies from the other domain in the case of cross-origin requests.

Syntax
------

    var myCred = request.credentials;

### Value

A `RequestCredentials` dictionary value indicating whether the user agent should send cookies from the other domain in the case of cross-origin requests. Possible values are:

-   `omit`: Never send or receive cookies.
-   `same-origin`: Send user credentials (cookies, basic http auth, etc..) if the URL is on the same origin as the calling script. **This is the default value.**
-   `include`: Always send user credentials (cookies, basic http auth, etc..), even for cross-origin calls.

This is similar to XHR’s `withCredentials` flag, but with three available values instead of two.

Example
-------

In the following snippet, we create a new request using the [`Request.Request()`](request) constructor (for an image file in the same directory as the script), then save the request credentials in a variable:

    var myRequest = new Request('flowers.jpg');
    var myCred = myRequest.credentials; // returns "same-origin" by default

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-credentials">Fetch<br />
<span class="small">The definition of 'credentials' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`credentials`

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

`default_same-origin`

72

18

61

No

55

12.1

72

72

Yes

No

12.2

11.0

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials</a>
