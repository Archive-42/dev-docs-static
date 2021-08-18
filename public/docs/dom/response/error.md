Response.error()
================

The `error()` method of the [`Response`](../response) interface returns a new `Response` object associated with a network error.

**Note**: This is mainly relevant to [ServiceWorkers](../service_worker_api); the error method is used to return an error if you so wish it. An error response has its [`type`](type) set to `error`.

**Note**: An "error" `Response` never really gets exposed to script: such a response to a [`fetch()`](../windoworworkerglobalscope/fetch) would reject the promise.

Syntax
------

    var errorResponse = Response.error();

### Parameters

None.

### Return value

A [`Response`](../response) object.

Example
-------

TBD (does not yet appear to be supported anywhere).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-response-error">Fetch<br />
<span class="small">The definition of 'error()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Response/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Response/error</a>
