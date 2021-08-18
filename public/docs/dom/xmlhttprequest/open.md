XMLHttpRequest.open()
=====================

The [`XMLHttpRequest`](../xmlhttprequest) method `open()` initializes a newly-created request, or re-initializes an existing one.

**Note:** Calling this method for an already active request (one for which `open()` has already been called) is the equivalent of calling [`abort()`](abort).

Syntax
------

    XMLHttpRequest.open(method, url[, async[, user[, password]]])

### Parameters

`method`  
The [HTTP request method](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods) to use, such as `"GET"`, `"POST"`, `"PUT"`, `"DELETE"`, etc. Ignored for non-HTTP(S) URLs.

`url`  
A [`DOMString`](../domstring) representing the URL to send the request to.

 `async` <span class="badge inline optional">Optional</span>   
An optional Boolean parameter, defaulting to `true`, indicating whether or not to perform the operation asynchronously. If this value is `false`, the `send()` method does not return until the response is received. If `true`, notification of a completed transaction is provided using event listeners. This *must* be true if the `multipart` attribute is `true`, or an exception will be thrown.

**Note:** Synchronous requests on the main thread can be easily disruptive to the user experience and should be avoided; in fact, many browsers have deprecated synchronous XHR support on the main thread entirely. Synchronous requests are permitted in [`Worker`](../worker)s.

 `user` <span class="badge inline optional">Optional</span>   
The optional user name to use for authentication purposes; by default, this is the `null` value.

 `password` <span class="badge inline optional">Optional</span>   
The optional password to use for authentication purposes; by default, this is the `null` value.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-open()-method">XMLHttpRequest<br />
<span class="small">The definition of 'open()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`open`

1

12

1

Starting in Firefox 30, synchronous requests on the main thread have been deprecated due to their negative impact on performance and the user experience. Therefore, the `async` parameter may not be `false` except in a `Worker`.

5

8

1.2

1

18

4

Starting in Firefox 30, synchronous requests on the main thread have been deprecated due to their negative impact on performance and the user experience. Therefore, the `async` parameter may not be `false` except in a `Worker`.

10.1

1

1.0

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)
-   Related [`XMLHttpRequest`](../xmlhttprequest) methods: [`setRequestHeader()`](setrequestheader),[`send()`](send), and [`abort()`](abort)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/open" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/open</a>
