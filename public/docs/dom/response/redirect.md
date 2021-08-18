Response.redirect()
===================

The `redirect()` method of the [`Response`](../response) interface returns a `Response` resulting in a redirect to the specified URL.

**Note**: This is mainly relevant to the [ServiceWorker API](../service_worker_api). A controlling service worker could intercept a page's request and redirect it as desired. This will actually lead to a real redirect if a service worker sends it upstream.

Syntax
------

    var response = Response.redirect(url, status);

### Parameters

`url`  
The URL that the new response is to originate from.

 `status` <span class="badge inline optional">Optional</span>   
An optional status code for the response (e.g., `302`.)

### Return value

A [`Response`](../response) object.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>RangeError</code></td><td>The specified status is not a redirect status.</td></tr><tr class="even"><td><code>TypeError</code></td><td>The specified URL is invalid.</td></tr></tbody></table>

Example
-------

    responseObj.redirect('https://www.example.com', 302);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-response-redirect">Fetch<br />
<span class="small">The definition of 'redirect()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

Yes

16

Yes

No

Yes

Yes

No

No

No

No

No

No

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Response/redirect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Response/redirect</a>
