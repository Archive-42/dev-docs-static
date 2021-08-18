Headers.get()
=============

The `get()` method of the [`Headers`](../headers) interface returns a byte string of all the values of a header within a `Headers` object with a given name. If the requested header doesn't exist in the `Headers` object, it returns `null`.

For security reasons, some headers can only be controlled by the user agent. These headers include the [forbidden header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name) and [forbidden response header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_response_header_name).

Syntax
------

    myHeaders.get(name);

### Parameters

`name`  
The name of the HTTP header whose values you want to retrieve from the `Headers` object. If the given name is not the name of an HTTP header, this method throws a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError). The name is case-insensitive.

### Returns

A [`ByteString`](../bytestring) sequence representing the values of the retrieved header or `null` if this header is not set.

Example
-------

Creating an empty `Headers` object is simple:

    var myHeaders = new Headers(); // Currently empty
    myHeaders.get('Not-Set'); // Returns null

You could add a header to this using [`Headers.append`](append), then retrieve it using `get()`:

    myHeaders.append('Content-Type', 'image/jpeg');
    myHeaders.get('Content-Type'); // Returns "image/jpeg"

If the header has multiple values associated with it, the byte string will contain all the values, in the order they were added to the Headers object:

    myHeaders.append('Accept-Encoding', 'deflate');
    myHeaders.append('Accept-Encoding', 'gzip');
    myHeaders.get('Accept-Encoding'); // Returns "deflate,gzip"

**Note**: [`Headers.getAll`](getall) used to have this functionality, with [`Headers.get`](get) returning only the first value added to the `Headers` object. The latest spec has removed `getAll()`, and updated `get()` to return all values.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-headers-get">Fetch<br />
<span class="small">The definition of 'get()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`get`

42

41

14

52

Prior to Firefox 52, `get()` only returned the first value in the specified header, with `getAll()` returning all values. From 52 onwards, `get()` now returns all values and `getAll()` has been deleted.

39

34

No

29

28

10.1

42

42

41

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Headers/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Headers/get</a>
